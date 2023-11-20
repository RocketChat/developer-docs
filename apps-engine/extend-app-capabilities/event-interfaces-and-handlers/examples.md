# Event Interface Examples

Now that we have learned about the event interfaces, let's go through some examples to implement them. On this page, we will follow three examples:

1. Messaging governance
2. Notify messages
3. Content inspection

## Messaging governance

In this example, we will use the `IPreMessageSentPrevent` interface to control whether a particular message should be sent to a channel. We are using our [Hello World app](../../getting-started/creating-an-app.md) to test this.

1. Open your app folder in Visual Studio and select the main app file, in this case, `HelloWorldApp.ts`.
2. To the `HelloWorldApp` class, add the `IPreMessageSentPrevent` interface as follows:

```typescript
export class TestApp extends App implements IPreMessageSentPrevent {
```

3. As soon as we add the indication of `implements IPreMessageSentPrevent` we see that Visual Studio displays an error that it cannot find the interface and shows the option to quickly fix it in a tooltip. Click it to display different import options that would fix the issue. Import the following interface:

{% code overflow="wrap" %}
```typescript
import { IPreMessageSentPrevent } from '@rocket.chat/apps-engine/definition/messages/IPreMessageSentPrevent';
```
{% endcode %}

4. Now Visual Studio will display an error that a certain method part of the interface has its implementation missing with the option to fix it quickly. Accept the suggested fix. Visual Studio adds two methods of the interface that are not implemented. The methods will throw an error when executed. But now, we have a skeleton code to work with:

```typescript
checkPreMessageSentPrevent?(message: IMessage, read: IRead, http: IHttp): Promise<boolean> {
        throw new Error('Method not implemented.');
    }
    executePreMessageSentPrevent(message: IMessage, read: IRead, http: IHttp, persistence: IPersistence): Promise<boolean> {
        throw new Error('Method not implemented.');
    }
```

5. With the `checkPreMessageSentPrevent` method, we will only check the messages from channels other than **general**. Visual Studio helps you navigate through the APIs of the classes of the objects by suggesting the available methods. For this example, you can see that the method variable `message` has a room attribute which has a `slugifiedName` string attribute. Update the method as follows:

```typescript
checkPreMessageSentPrevent?(message: IMessage, read: IRead, http: IHttp): Promise<boolean> {
        return message.room.slugifiedName != 'general';
    }
```

6. Now Visual Studio displays an error that the method signature is not compatible with returning a `Promise<boolean>`. To fix this issue, add `async` to the method signature.
7. Next, implement the `executePreMessageSentPrevent` method. If the message equals "test", we prevent it from being published.
8. Your main app file should look something like this:

{% code lineNumbers="true" fullWidth="true" %}
```typescript
import {
    IAppAccessors,
    IHttp,
    ILogger,
    IPersistence,
    IRead,
} from '@rocket.chat/apps-engine/definition/accessors';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IMessage } from '@rocket.chat/apps-engine/definition/messages';
import { IPreMessageSentPrevent } from '@rocket.chat/apps-engine/definition/messages/IPreMessageSentPrevent';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';

export class HelloWorldApp extends App implements IPreMessageSentPrevent {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
        logger.debug('Hello, World!');
    }
    
    async checkPreMessageSentPrevent?(message: IMessage, read: IRead, http: IHttp): Promise<boolean> {
        return message.room.slugifiedName != 'general';
    }
    
    async executePreMessageSentPrevent(message: IMessage, read: IRead, http: IHttp, persistence: IPersistence): Promise<boolean> {
        return message.text == 'test';
    }
}
```
{% endcode %}

9. Save the file and deploy your app.&#x20;
10. If we send the `‘test’` message in a channel other than **general**, it should not be published (it will appear grayed out). If the message is something different it will get sent. As for the room **general**, all messages will be sent including `‘test’` as shown in the following screenshots:

<div align="left">

<figure><img src="https://lh5.googleusercontent.com/DfNAWhdSsUbrXSQNI0Us3dffbntvzNhGPfHXRYn-8cGbWlj3zZiKm7nKVzn6KIQzfMoxz3zFGT-bHjJtGAEC_5r8b1AXgYgGaUUzLEwUstKSw8TPsdWOADidSa5BBanSqWiQ7_iqxg-VNVcfjvXPByk" alt=""><figcaption></figcaption></figure>

</div>

<div align="left">

<figure><img src="https://lh4.googleusercontent.com/dFCTutpqP_AF3a1BzY-9L5f3eew47IMSfgqBPY2AGFMJF6B0At5feUhwI6e3afyYcM5uEKJnyJKvElEVBQ2_9NUl_4DMD04rhkgKDl37j0EvzmQoj38bohFQvzjLIaXI2_wocleADA6qMUcPf-YQReo" alt=""><figcaption></figcaption></figure>

</div>

## Notify messages

In this example, we will notify the **general** channel whenever a message is sent anywhere else. Here we will implement the `IPostMessageSent` interface.

1. Like the previous example, in the main app file (in this case, `HelloWorldApp.ts`), we will add the `check` and `execute` methods from the `IPostMessageSent` interface as shown in the code below.
2. The `check` method confirms that the **general** channel exists and fetches it.
3. In the `execute` method, for the **general** channel, we create a message containing information about the message published, the room, and the sender by getting the values from `sendMessage`. The `messageBuilder` allows us to define richly formatted messages.&#x20;

{% code lineNumbers="true" fullWidth="true" %}
```typescript
import {
   IAppAccessors,
   IHttp,
   ILogger,
   IModify,
   IPersistence,
   IRead,
} from '@rocket.chat/apps-engine/definition/accessors';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IMessage, IPostMessageSent } from '@rocket.chat/apps-engine/definition/messages';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';
import { IRoom } from '@rocket.chat/apps-engine/definition/rooms/IRoom';
import { IUser } from '@rocket.chat/apps-engine/definition/users/IUser';

export class HelloWorldApp extends App implements IPostMessageSent {
   constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
       super(info, logger, accessors);
       logger.debug('Hello, World!');
   }
   
   async checkPostMessageSent?(message: IMessage, read: IRead, http: IHttp): Promise<boolean> {
       return message.room.slugifiedName != 'general';
   }
   
   async executePostMessageSent(message: IMessage, read: IRead, http: IHttp, persistence: IPersistence, modify: IModify): Promise<void> {
       const general = await read.getRoomReader().getByName('general');
       if (!general) {
           return;
       }
       const msg = `@${message.sender.username} said "${message.text}" in #${message.room.displayName}`;
       const author = await read.getUserReader().getAppUser();
       await this.sendMessage(general, msg, author?author:message.sender, modify);
   }
   
   private async sendMessage(room: IRoom, textMessage: string, author: IUser, modify: IModify) {
       const messageBuilder = modify.getCreator().startMessage({
           text: textMessage,
       } as IMessage);
       messageBuilder.setRoom(room);
       messageBuilder.setSender(author);
       return modify.getCreator().finish(messageBuilder);
   }
}
```
{% endcode %}

4. Now save, deploy, and test the app. You should be able to see the warning messages posted to the **general** channel when writing to any other channel.

<div align="left">

<figure><img src="https://lh5.googleusercontent.com/ewAq6AbbvEsLGW7Bk3orChVhTNkPqjuzZ6qvTMWNW2gdOVTvYa77Z0SMRKy-lQgzDPPB61ScAUI3KhyAxkzeFc-s48UCaLfMfBZiaXjYh93fGSE0Kaf86I5odzebjijuLI0rW0pAKzw53zLrQT019R4" alt=""><figcaption></figcaption></figure>

</div>

## Content inspection

A typical use case of the previous two examples is to control the content of the information being exchanged. For instance, we could use regular expressions matching inappropriate words to flag them.

Some apps that implement content inspection are:

* [Data Loss Prevention (DLP)](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/data-loss-prevention-dlp-app)
* [Antivirus (ClamAV)](https://docs.rocket.chat/use-rocket.chat/user-guides/security-bundle/antivirus-clamav-app)
* [Word Replacer](https://www.rocket.chat/apps/word-replacer)

For our Hello World app, let's look into inspecting file attachments.&#x20;

1. In our main app file, we will implement `IPreFileUpload` and print a message notifying the user that the attached file is inspected.
2. If the file type is `text/plain`, we will log the file's content also.

{% code lineNumbers="true" fullWidth="true" %}
```typescript
import {
    IAppAccessors,
    IHttp,
    ILogger,
    IModify,
    IPersistence,
    IRead,
} from '@rocket.chat/apps-engine/definition/accessors';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { AppMethod, IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';
import { IRoom } from '@rocket.chat/apps-engine/definition/rooms/IRoom';
import { IFileUploadContext, IPreFileUpload } from '@rocket.chat/apps-engine/definition/uploads';
import { IUser } from '@rocket.chat/apps-engine/definition/users/IUser';

export class HelloWorldApp extends App implements IPreMessageSentPrevent, IPostMessageSent, IPreFileUpload {
    public async [AppMethod.EXECUTE_PRE_FILE_UPLOAD](context: IFileUploadContext, read: IRead, http: IHttp, persis: IPersistence, modify: IModify): Promise<void> {
        console.log('ContentInspectionExampleAppApp - File Uploaded - Name: ' + context.file.name);
        console.log('ContentInspectionExampleAppApp - File Uploaded - Type: ' + context.file.type);
        console.log('ContentInspectionExampleAppApp - File Uploaded - Size: ' + context.file.size);
 

        if (context.file.type == 'text/plain') {
            console.log('ContentInspectionExampleAppApp - File Uploaded - Content: ' +
                String.fromCharCode.apply(null, context.content));
        }3. 

        //if file was bad we could throw an exception
        //throw new FileUploadNotAllowedException('File is Bad');
        const user = await read.getUserReader().getById(context.file.userId);
        const room = await read.getRoomReader().getById(context.file.rid);
        if (room) {
            await this.notifyMessage(room, read, user, 'File inspected - Check logs');
        }
    }
    
    private async notifyMessage(room: IRoom, read: IRead, sender: IUser, message: string): Promise<void> {
        const notifier = read.getNotifier();
        const messageBuilder = notifier.getMessageBuilder();
        messageBuilder.setText(message);
        messageBuilder.setRoom(room);
        return notifier.notifyUser(sender, messageBuilder.getMessage());
    }
}
```
{% endcode %}

3. Save the file, deploy, and test the app. The notification is like a temporary private message visible only to the user who sent the attachment (if you refresh the page, the notification is gone).&#x20;

<div align="left">

<figure><img src="https://lh5.googleusercontent.com/2YmtCb8p1fqkm3Z4gqhCeGmuuIdSaM4wDx0RjCW51WtRXsMqX-FdrADg-n7_mIk1WHdKRPsvfgNa0HG0pru9Hli-_FMzb6BxC_2jONvAFR8dApCCFPE4hkjNbTEYdajKxwKGbBNMXsTBaYX2KFJfpkE" alt=""><figcaption></figcaption></figure>

</div>

Great! With these examples, you have learned how to implement event interfaces and react to certain events. You have made significant progress in expanding your app!

In the upcoming sections, we will look at another way to extend your app's capabilities by creating interactive user experiences with the Apps-Engine UIKit.
