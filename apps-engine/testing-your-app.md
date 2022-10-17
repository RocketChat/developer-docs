---
description: How to test your app
---

# Testing your App

This guide shows you how to run a unit test on your app.

## Requirements

Please make sure you meet the following dependencies. Visit the corresponding sites to follow how to set them up.

* [Jest](https://www.npmjs.com/package/jest)
* [@Types/Jest](https://www.npmjs.com/package/@types/jest)

This guide is given with the assumption you have some knowledge of:

* Typescript
* Basic unit testing concepts

## App Setup

On your `.rcappsconfig` add the following lines on the `ignoredFiles` array:

1. **"/mocks/\*"**
2. **"/tests/\*"**
3. **"\*\*/jest.config.js"**

## Testing

Say for example you have this app command to test:

{% code title="HelpCommand.ts" %}
```typescript
import { IModify, IRead } from "@rocket.chat/apps-engine/definition/accessors";
import { SlashCommandContext } from "@rocket.chat/apps-engine/definition/slashcommands";
import { notifyUser } from "../lib/message";
import { BoilerplateApp } from "../BoilerplateApp";

class HelpCommand {
    public async run({ app, context, read, modify }: { app: BoilerplateApp, context: SlashCommandContext, read: IRead, modify: IModify }): Promise<void> {
        const room = context.getRoom();
        const user = context.getSender();

        const text =
                `\`/boilerplate modal\` Opens a modal\n` +
                `\`/boilerplate help\` Shows help message`;

        await notifyUser({ app, read, modify, room, user, text });
    }
}

export const helpCommand = new HelpCommand();
```
{% endcode %}

### Snippet Explanation

It's a common command that shows a helper to the user on how to use your app. First, decide what you want to test, and then you will see how.

This class `HelpCommand` has a single `async` method called **run.** Let's see how it works.

On both lines 8 and 9, the method is using the context parameter to get some information regarding room and sender.

On line 11 we just assign a string to a const and at the end of the method, it calls a function called `notifyUser` which sends the message to the user.

### Testing

At the top of the file, set `jest.autoMockOff();` and below will have an example on how to test your command and the explanation of what is happening on each line/block of code.

{% code title="HelpCommand.spec.ts" %}
```typescript
jest.autoMockOff(); //1
const notifyUser = jest.fn();
jest.mock('@lib/message', () => ({ //2
    notifyUser,
}));
import { 
   commandsMockParams,
   roomMock,
   userMock 
} from '@commands/__mocks__/commands.mock'; //3

import { helpCommand } from '@commands/HelpCommand'; //4

describe('HelpCommand', () => { //5
    test('should set tex with the right values', async () => { //6
       await helpCommand.run(commandsMockParams); //7
       const { app, modify, read } = commandsMockParams; //8
       expect(notifyUser).toBeCalledWith({ 
          app,
          read,
          modify,
          room: roomMock,
          text:
           `\`/boilerplate modal\` Opens a modal\n` +
           `\`/boilerplate help\` Shows help message`,
         user: userMock,
       }); //9
    });
});
```
{% endcode %}

1. The first step is very since it depends on how you set your `jest.setup.js` sometimes auto mock may help and sometimes not;
2. This part covers lines 3..5 which is the part that you will mock the method is called at the end of your method **run**;

{% hint style="info" %}
The `jest.mock` will mock all methods/functions that are inside the path inserted on the parameter and the `jest.fn()` attributed on `notifyUser` allows you to test in your test case.

For deep documentation about mock a method please check [here](https://jestjs.io/docs/mock-functions)**.**
{% endhint %}

3\. This part is just a form to organize all the mocks you will use on your test, since the **run** method need some parameters that have a lot of properties you may separate this on a file, below you will see an example:

{% code title="commands.mock" %}
```typescript
const roomMock = {
    id: '123',
    displayName: 'nice display name',
    slugifiedName: 'slugfied name',
    type: 'type',
    creator: {},
    userIds: ['123', '234'],
    isDefault: true,
    isReadOnly: false,
    displaySystemMessages: true,
    messageCount: 1,
    createdAt: 'Mon Nov 22 2021 15:22:49 GMT-0300 (Brasilia Standard Time)',
    updatedAt: 'Mon Nov 22 2021 15:22:49 GMT-0300 (Brasilia Standard Time)',
    lastModifiedAt: 'Mon Nov 22 2021 15:22:49 GMT-0300 (Brasilia Standard Time)',
    description: 'desc',

};

const userMock = {
    id: '567',
    username: 'username',
    emails: [],
    type: 'nice type',
    isEnabled: true,
    name: 'name',
    roles: 'admin',
    status: 'Registered',
    statusConnection: 'Online',
    utcOffset: 'ZM',
    createdAt: 'Mon Nov 22 2021 15:22:49 GMT-0300 (Brasilia Standard Time)',
    updatedAt: 'Mon Nov 22 2021 15:22:49 GMT-0300 (Brasilia Standard Time)',
    lastLoginAt: 'Mon Nov 22 2021 15:22:49 GMT-0300 (Brasilia Standard Time)',
    appId: '678',
};
const commandsMockParams: { 
    app: WikipediaApp,
    context: SlashCommandContext,
    read: IRead,
    modify: IModify,
    http: IHttp
} = {
    app: {
        initialize: jest.fn(),
    } as unknown as WikipediaApp,
    context: {
        getSender: jest.fn().mockReturnValue(userMock),
        getRoom: jest.fn().mockReturnValue(roomMock),
        getArguments: jest.fn().mockReturnValue(args),
        getThreadId: jest.fn(),
        getTriggerId: jest.fn(),
    } as unknown as SlashCommandContext,
    .
    .
    .
    .
    .
```
{% endcode %}

4\. Next, you only need to import the function or class that needs to be tested;

5\. Set your `describe` to identify your test, for this example `HelpCommand` is fine;

6\. At this point, you will describe your test cases, for this example, one is enough but it can be more, thinking that you may need to test multiple cases as errors or forks.

The `test` receives a string and a callback to run the test.

{% hint style="info" %}
In some cases, the method/function that you are testing may be a Promise, so you can set the callback as async it will work in most of the cases, but some not, so for more information about testing async methods, please reach this [link](https://jestjs.io/docs/asynchronous)
{% endhint %}

7\. This line you only need to call your method/function and in this particular case this is a void method it will be no need to attribute the result of your method in a variable;

8\. This part only takes all the mocked values to check our methods;

9\. This is the famous `expect` where you check if your method is working as it is supposed to do, in this case, we are checking if the notifyUser is been called with the right parameters.

### Running your test

Run your test by following any of the two procedures

* **Using Terminal**: Open up your terminal in the working directory and execute `jest <file-name>` or just `jest` to run all test files;
* **Using the VScode extension**: You only need to install [this](https://marketplace.visualstudio.com/items?itemName=firsttris.vscode-jest-runner) vscode extension and all of your tests files appear as below:

![Using extension to run the tests](<../.gitbook/assets/image (85) (1).png>)

Two buttons will appear upon tests so you can click run or debug and if everything went well you will see:

![All tests succeed](<../.gitbook/assets/Screenshot from 2021-11-23 16-50-46.png>)

For more information on how to run your tests please visit this [link](https://jestjs.io/pt-BR/docs/cli).

## Conclusion

This documentation does not show all you can do with jest. Feel free to check out Jest documentation for other samples.
