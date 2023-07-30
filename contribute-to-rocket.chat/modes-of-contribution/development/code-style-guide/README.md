---
description: Rocket.Chat project's code style
---

# Code Style Guide

This guide aims to provide a clear understanding of the Rocket.Chat project's code style, enabling contributors to effectively participate in the project. Before diving into the code, it's important to understand the [development-workflow.md](../development-workflow.md "mention") of Rocket.Chat. It covers aspects such as issue assignment, pull request process, and branching strategies. The Rocket.Chat Code Style Guide provides further guidelines to maintain consistency and quality in the codebase.

Key points include:

1. **Language and UI Engine:** TypeScript is now the default language for projects.&#x20;
2. **Component Library:** The [Fuselage](https://github.com/RocketChat/Rocket.Chat.Fuselage), a component library based on React, is used for Rocket.Chat UI. Check it out when contributing to the Rocket.Chat UI and feel free to contribute new components or fixes.
3. **Best Practices:** Most of the coding standards are covered by ESLint configured at [.eslintrc](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.eslintrc), and most of them came from our own [ESLint Config Package](https://github.com/RocketChat/eslint-config-rocketchat).

Things not covered by `eslint`:

* Prefer longer/descriptive variable names, e.g. `error` vs `err`, unless dealing with common record properties already shortened, e.g. `rid` and `uid`
* Use return early pattern. [See more](https://blog.timoxley.com/post/47041269194/avoid-else-return-early)
* Prefer `Promise` over `callbacks`
* Prefer `await` over `then/catch` (also valid for unit/e2e test callbacks)
* Queries should be created inside models, not outside. The query description should be inside the model class.
* &#x20;Avoid hardcoding fields inside models. The same method can be used for different purposes, using different fields.
* &#x20;Prefer creating and calling REST endpoints over Meteor methods.
* v1 REST endpoints should follow the following pattern: `/api/v1/dashed-namespace.camelCaseAction`
* Avoid "internal" `Meteor.call` . Server code should not use `Meteor.call`.&#x20;
* Before submitting a PR you should get no errors on `eslint`. To check your files run:

```
yarn lint
```

{% hint style="success" %}
We provide a[ .editorconfig](https://github.com/RocketChat/Rocket.Chat/blob/develop/.editorconfig) and an [.eslintrc](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.eslintrc), file that will help you to keep some standards in place.
{% endhint %}

4. **Testing:** Two types of tests are run on Rocket.Chat: Unit tests and End to End tests. The major difference is that End to End tests require a Rocket.Chat instance running to execute the API and UI checks.

* **End-to-End Tests**: First, you need to run a Rocket.Chat server on **Test Mode** and on an **Empty Database**:

```
# Running with a local mongodb database
MONGO_URL=mongodb://locEnd-to-Endty MONGO_OPLOG_URL=mongodb://localhost/local TEST_MODE=true meteor
```

```
# Running with a local mongodb database but cleaning it before
mongo --eval "db.dropDatabase()" empty && MONGO_URL=mongodb://localhost/empty MONGO_OPLOG_URL=mongodb://localhost/local TEST_MODE=true meteor
```

Now you can run the tests in the `apps/meteor` folder with:

```
yarn test:e2e
```

* **Unit Tests**: Unit tests are simpler to set up and run. They do not require a working Rocket.Chat instance.

```
yarn testunit
```

It's possible to run on watch mode as well in the `apps/meteor` folder with:

```
yarn testunit-watch
```

{% hint style="danger" %}
1. Before pushing your code or submitting a Pull Request, it's crucial to run the lint and tests. If these steps are skipped, your contribution might fail the Continuous Integration (CI) checks, causing delays in the review process. Reviewers will then need to request fixes, which further postpone the evaluation of your contribution
2. &#x20;Rocket.Chat uses [husky](https://www.npmjs.com/package/husky) to run the **lint** and **unit tests** before proceeding to the code push process, so you may notice a delay when pushing your code to your repository.
{% endhint %}

5. **PR Titles:** PR titles are used when creating the changelog. Keep them short, concise, and user-focused. Use appropriate tags to describe your PR (e.g., fix:, feat:, etc.). For more information, please refer to these resources:[#3.-branching-and-pull-requests](../development-workflow.md#3.-branching-and-pull-requests "mention")  [#4.-adding-changeset-to-your-pull-request](../development-workflow.md#4.-adding-changeset-to-your-pull-request "mention") and for deeper understanding visit [pull-requests-tags.md](../pull-requests-tags.md "mention")
6. **Security Best Practices**: In the process of developing APIs, it's crucial to maintain a strong focus on data security and efficiency. This means you should avoid exposing any unnecessary data in the API responses. When it's required to expose sensitive data, always ensure that the appropriate permissions are checked or new ones are created. It's also important to remember that any new APIs should always have rate limiters in place to prevent abuse and maintain service stability. User data handling is another critical aspect. When rendering data, user input should always be properly escaped to prevent potential security vulnerabilities such as injection attacks. On the server side, it's essential to impose restrictions on the size of the user input to prevent excessive data load. Furthermore, even if validations are being executed on the client side, they should always be mirrored and executed on the server side as well. This dual validation approach ensures data integrity and security, as client-side validations can be bypassed.
7. **Performance Best Practices**: When interacting with the database, it's recommended to specify only the necessary fields in your queries rather than retrieving full documents. This approach enhances performance and reduces unnecessary data load. Additionally, it's important to limit the number of records returned by a query to a reasonable amount to prevent overwhelming the system with excessive data. Indexing is another crucial aspect of database management. Always ensure your queries are utilizing indexes for faster data retrieval. If they're not, it's advisable to create new indexes to improve query performance. In terms of task execution, favor the use of queues over long-running executions. This approach helps manage system resources more efficiently and improves overall performance. Monitoring is also key in maintaining a healthy system. Therefore, create new metrics whenever possible to measure various aspects of the system. This will provide valuable insights and help identify potential areas for improvement. Lastly, make use of caching whenever possible. Caching data and responses can significantly reduce load times and server demand, leading to a more responsive and efficient system.
8. **Contributor License Agreement:** To have your contribution accepted, you must sign the  [Contributor License Agreement](https://cla-assistant.io/RocketChat/Rocket.Chat). In case you submit a Pull Request before signing the CLA GitHub will alert you with a new comment asking you to sign and will block the Pull Request from being merged by us. Please review and sign our CLA at [https://cla-assistant.io/RocketChat/Rocket.Chat](https://cla-assistant.io/RocketChat/Rocket.Chat)
