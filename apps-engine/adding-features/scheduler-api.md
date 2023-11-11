# Scheduler API

The Scheduler API gives apps the possibility of creating tasks that run in a defined schedule. It can be a one-time event or a recurring task. It uses [agenda.js](https://github.com/agenda/agenda) as the backend, so the [schedule syntax](https://github.com/agenda/human-interval) and internal processes are all according to its documentation.

See the details on the API in the [Module scheduler](https://rocketchat.github.io/Rocket.Chat.Apps-engine/modules/scheduler.html) definition. There's also an [example app](https://github.com/RocketChat/Apps.RocketChat.Tester/tree/scheduler) that can be used as a guide.

## Add permissions

As per the [Permission System](https://developer.rocket.chat/apps-engine/getting-started/permission-system), the Schedule API needs the following permission in your app's manifest (`app.json` file):

```json
{
  permissions: [
    { "name": "scheduler" }
  ]
}
```

## Register jobs (processors)

To use the Scheduler API you'll need two things:&#x20;

* The functions to be run as jobs (we call them `processors`).
* The schedule in which they run.&#x20;

This is configured in the app's `extendConfiguration` method. During the app's startup, the processors are registered to make them available for scheduling.

{% code lineNumbers="true" %}
```typescript
public async extendConfiguration(configuration: IConfigurationExtend) {
    configuration.scheduler.registerProcessors([
        {
            id: 'first',
            processor: async (jobData) => console.log(`[${ Date() }] this is a task`, jobData),
        },
    ]);
}
```
{% endcode %}

The `processor` is an `async` function and can receive arguments (`jobData`). The arguments are passed during scheduling.

## Start a job

To trigger the registered processor as a job, you must provide:

* The `id` of the processor.
* The type of job it will be. The available types are `scheduleRecurring` (the job runs in an `interval`) and `scheduleOnce` (the job runs once using the `when` keyword).

Starting a job can be done when running a slash command, for example:

{% code lineNumbers="true" %}
```typescript
// slashcommand class
public async executor(context: SlashCommandContext, read: IRead, modify: IModify): Promise<void> {
    // SCHEDULING A RECURRING TASK
    const task = {
        id: 'first',
        interval: '10 seconds',
        data: { test: true },
    };
    await modify.getScheduler().scheduleRecurring(task);

    // SCHEDULING ONETIME TASK
    const task = {
        id: 'first',
        when: '8 seconds',
    };
    await modify.getScheduler().scheduleOnce(task);
}
```
{% endcode %}

You can also trigger a job as soon as it gets registered, without the need for manual or automated triggering. When you register your processor in the `extendConfiguration` method, you can pass a prop called `startupSetting` in the processor's object:

{% code lineNumbers="true" %}
```typescript
import { StartupType } from '@rocket.chat/apps-engine/definition/scheduler';
// ...

configuration.scheduler.registerProcessors([
    {
        id: 'first',
        processor: async (jobData) => console.log(`[${ Date() }] this is a task`, jobData),
        startupSetting: {
          type: StartupType.ONETIME,
          when: '20 seconds',
          data: { test: true },
        }
    },
    {
        id: 'second',
        processor: async (jobData) => console.log(`[${ Date() }] this is a task`, jobData),
        startupSetting: {
          type: StartupType.RECURRING,
          interval: '20 seconds',
        }
    },
]);
```
{% endcode %}

This indicates that you want that particular processor to be scheduled as soon as it is registered. You can define the "immediate scheduling" as a recurring job (`StartupType.RECURRING`) or a one-time job (`StartupType.ONETIME`). You can also pass data using the `data` object. It will work just like when you schedule a task using the `modify` accessor.

Here, `data` is not something that's passed to the processor or a function as a living object or executable code. This `data` is a static piece of data that is passed to the processor's first argument.

The signature of the processor function is as follows:

{% code overflow="wrap" %}
```typescript
(jobContext: IJobContext, read: IRead, modify: IModify, http: IHttp, persis: IPersistence) => Promise<void>
```
{% endcode %}

The first argument is the data object you're passing when actually scheduling the job; (`[k: string]:any`). The rest of the arguments are passed when the function is run.

## Cancel a job

To stop a job, all you have to do is pass the ID of the job you want to stop:

```typescript
const jobId = 'first';
await modify.getScheduler().cancelJob(jobId);
```

It will stop the running job (if any).

## Cancel all jobs from the app

To stop all the current running jobs from the app:

```typescript
await modify.getScheduler().cancelAllJobs();
```
