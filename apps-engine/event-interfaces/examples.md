# Examples

### Messaging Governance

* We will be using the `IPreMessageSentPrevent` to control if a certain message should be sent or not into a channel.&#x20;
* As soon as we add the indication of the ‘implements `IPreMessageSentPrevent`‘ we see that Visual Studio complains that it cannot find the interface and shows in a tooltip the option to quickly fix it. Click it to display different import options that would fix the issue. We would choose the second one that would import just that specific interface.
* Now it will complain that a certain method part of the interface has its implementation missing again with the option to fix it quickly. Accept the fix suggested by including a skeleton implementation of the method.&#x20;
* Visual Studio added the two methods of the interface. None of them are really implemented and would throw an error when executed. But now we have a skeleton code to work with.&#x20;
* Let’s say we would want to only check the messages from channels different from ‘general’. We will update the `checkPreMessageSentPrevent` method.&#x20;
* Visual Studio helps you out to navigate through the API of the classes of the objects by suggesting the methods available so you can easily see for example that the method variable message has a room attribute which in its turn has a slugifiedName string attribute.&#x20;
* As you will see after updating the code Visual Studio will complain that the method signature is not compatible with returning a `Promise<boolean>`.&#x20;
* The quick way to fix this common issue while coding is to add the async to the method signature. Basically, we are doing the same as before. Return true only for rooms that are not ‘general’.&#x20;
* Now we need to implement the actual `executePreMessageSentPrevent` method. In this case, if the message will equal ‘test’ we prevent it from getting published we will allow it.

```typescript
export class TestApp extends App implements IPreMessageSentPrevent {
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
```

Now after saving, we can deploy our app again as usual and test it. If we write the ‘test’ message in a channel different than general it should not be published (it will show as grayed out) and if the message is something different it will get sent. While for the room general, all messages will be sent including ‘test’.

<div align="left">

<figure><img src="https://lh5.googleusercontent.com/DfNAWhdSsUbrXSQNI0Us3dffbntvzNhGPfHXRYn-8cGbWlj3zZiKm7nKVzn6KIQzfMoxz3zFGT-bHjJtGAEC_5r8b1AXgYgGaUUzLEwUstKSw8TPsdWOADidSa5BBanSqWiQ7_iqxg-VNVcfjvXPByk" alt=""><figcaption></figcaption></figure>

</div>

<div align="left">

<figure><img src="https://lh4.googleusercontent.com/dFCTutpqP_AF3a1BzY-9L5f3eew47IMSfgqBPY2AGFMJF6B0At5feUhwI6e3afyYcM5uEKJnyJKvElEVBQ2_9NUl_4DMD04rhkgKDl37j0EvzmQoj38bohFQvzjLIaXI2_wocleADA6qMUcPf-YQReo" alt=""><figcaption></figcaption></figure>

</div>

### Notify Messages

* This one corresponds to after a message is published. We will use it for example to inform on channel ‘general’ about any message published anywhere else.&#x20;
* Add the interface as shown in the previous example, fix imports, and add methods.&#x20;
* Now we need to add code to the first two methods. Here we are basically fetching the general room and confirming it exists.&#x20;
* Then we create a message for the room general with text information on the message published and the room and user.&#x20;
* We could also change a bit the code for the message in general to show up as sent by the user who wrote the original message in the other channel. Note that in this case we are calling the `setSender` method on the message builder and using the sender of the original message as value.

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
import { IPreMessageSentPrevent } from '@rocket.chat/apps-engine/definition/messages/IPreMessageSentPrevent';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';
import { IRoom } from '@rocket.chat/apps-engine/definition/rooms/IRoom';
import { IUser } from '@rocket.chat/apps-engine/definition/users/IUser';


export class TestApp extends App implements IPreMessageSentPrevent, IPostMessageSent {
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
       this.sendMessage(general, msg, author?author:message.sender, modify);
   }
   async checkPreMessageSentPrevent?(message: IMessage, read: IRead, http: IHttp): Promise<boolean> {
       return message.room.slugifiedName != 'general';
   }
   async executePreMessageSentPrevent(message: IMessage, read: IRead, http: IHttp, persistence: IPersistence): Promise<boolean> {
       return message.text == 'test';
   }
   sendMessage(room: IRoom, textMessage: string, author: IUser, modify: IModify) {
       const messageBuilder = modify.getCreator().startMessage({
           text: textMessage,
       } as IMessage);
       messageBuilder.setRoom(room);
       messageBuilder.setSender(author);
       modify.getCreator().finish(messageBuilder);
   }
}
```

The message builder allows us to define richly formatted messages. Now if we save, deploy, and test you should be able to see the warning messages posted to the general channel when writing to any other channel.&#x20;

<div align="left">

<figure><img src="https://lh5.googleusercontent.com/ewAq6AbbvEsLGW7Bk3orChVhTNkPqjuzZ6qvTMWNW2gdOVTvYa77Z0SMRKy-lQgzDPPB61ScAUI3KhyAxkzeFc-s48UCaLfMfBZiaXjYh93fGSE0Kaf86I5odzebjijuLI0rW0pAKzw53zLrQT019R4" alt=""><figcaption></figcaption></figure>

</div>

<div align="left">

<figure><img src="https://lh4.googleusercontent.com/RfA1fwUDng4kJ-L442oTjMxnHTcvB_33ZvHCkJy2XebmfiXmVptrQ9hU7EE-R9EZWedpPbdZII2rxAe4DpM6x57QNu3pX9sWR1RqL4fA8d8B8XaOAdrM1tXT_yf_gt0B3dey4t-AoYhdfnavdN16IBg" alt=""><figcaption></figcaption></figure>

</div>

### Content Inspection

A typical use case is to control content information being exchanged. So in the example before we could be paying attention to regular expressions matching inappropriate words, or for PIIF, or for virus for example.&#x20;

Example apps:

* [Data Loss Prevention (DLP)](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/data-loss-prevention-dlp-app)
* [Antivirus (ClamAV)](https://docs.rocket.chat/use-rocket.chat/user-guides/security-bundle/antivirus-clamav-app)
* [Word Replacer](https://www.rocket.chat/apps/word-replacer)

We already built with the two interfaces a message text content kind of inspector but for the sake of completeness let’s look into the case of inspecting file attachments (as for example the Antivirus example app before does more throughout through integration with ClamAV).

#### `IPreFileUpload`&#x20;

So the `IPreFileUpload` would be the next Interface we would want to implement. We won't be preventing the attachment of files but in the case of plain text files, we will print the messages out into the logs of Rocket.Chat server.

```typescript
export class TestApp extends App implements IPreMessageSentPrevent, IPostMessageSent, IPreFileUpload {
   constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
       super(info, logger, accessors);
       logger.debug('Hello, World!');
   }
   async [AppMethod.EXECUTE_PRE_FILE_UPLOAD](context: IFileUploadContext, read: IRead, http: IHttp, persis: IPersistence, modify: IModify): Promise<void> {
       console.log('ContentInspectionExampleAppApp - File Uploaded - Name: ' + context.file.name);
       console.log('ContentInspectionExampleAppApp - File Uploaded - Type: ' + context.file.type);
       console.log('ContentInspectionExampleAppApp - File Uploaded - Size: ' + context.file.size);


       if (context.file.type == 'text/plain') {
           console.log('ContentInspectionExampleAppApp - File Uploaded - Content: ' +
               String.fromCharCode.apply(null, context.content));
       }


       //if the file was bad we could throw an exception
       //throw new FileUploadNotAllowedException('File is Bad');
   }
```

As you can see we will always be logging some info on the file but if it’s a text/plain we will log its contents also. The next step is to upload and test.&#x20;

<div align="left">

<figure><img src="https://lh6.googleusercontent.com/ExEYBqRy7ypZ_tx0XfNHDNKenM5jsOjjQq0e8ywS95SPzHnzq4CpqooYSZt7Fvsdnwo5dnbzgi_zXGnCHYJBECT1sHlx7CFcvI_Ap7JiS47s0939sWPDPVBgSmkn2a3mutmskaS9p57KWRps2yPyJAM" alt=""><figcaption></figcaption></figure>

</div>

```typescript
async [AppMethod.EXECUTE_PRE_FILE_UPLOAD](context: IFileUploadContext, read: IRead, http: IHttp, persis: IPersistence, modify: IModify): Promise<void> {
       console.log('ContentInspectionExampleAppApp - File Uploaded - Name: ' + context.file.name);
       console.log('ContentInspectionExampleAppApp - File Uploaded - Type: ' + context.file.type);
       console.log('ContentInspectionExampleAppApp - File Uploaded - Size: ' + context.file.size);


       if (context.file.type == 'text/plain') {
           console.log('ContentInspectionExampleAppApp - File Uploaded - Content: ' +
               String.fromCharCode.apply(null, context.content));
       }


       //if file was bad we could throw an exception
       //throw new FileUploadNotAllowedException('File is Bad');
       const user = await read.getUserReader().getById(context.file.userId);
       const room = await read.getRoomReader().getById(context.file.rid);
       if (room) {
           this.notifyMessage(room, read, user, 'File inspected - Check logs');
       }
   }
   async notifyMessage(room: IRoom, read: IRead, sender: IUser, message: string): Promise<void> {
       const notifier = read.getNotifier();
       const messageBuilder = notifier.getMessageBuilder();
       messageBuilder.setText(message);
       messageBuilder.setRoom(room);
       notifier.notifyUser(sender, messageBuilder.getMessage());
   }

```

Now still for the case of the file let’s notify the user attaching the file that the file was inspected. A notification is like a private temporary message (if you refresh the page the notification is gone) to the user only. If we test now by attaching a file we should see:

<div align="left">

<figure><img src="https://lh5.googleusercontent.com/2YmtCb8p1fqkm3Z4gqhCeGmuuIdSaM4wDx0RjCW51WtRXsMqX-FdrADg-n7_mIk1WHdKRPsvfgNa0HG0pru9Hli-_FMzb6BxC_2jONvAFR8dApCCFPE4hkjNbTEYdajKxwKGbBNMXsTBaYX2KFJfpkE" alt=""><figcaption></figcaption></figure>

</div>
