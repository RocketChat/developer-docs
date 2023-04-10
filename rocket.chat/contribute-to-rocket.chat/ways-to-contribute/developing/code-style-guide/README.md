# Code Style Guide

{% hint style="success" %}
We provide a[ .editorconfig](https://github.com/RocketChat/Rocket.Chat/blob/develop/.editorconfig) and an [.eslintrc](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.eslintrc), file that will help you to keep some standards in place.
{% endhint %}

### ECMAScript vs TypeScript

We are currently adopting TypeScript as the default language on our projects, the current codebase will be migrated incrementally from JavaScript to TypeScript.

While we still have a couple of JavaScript files you should not create new ones. As much as possible new code contributions should be in **TypeScript**.

### Blaze vs React

We are currently adopting React over Blaze as our UI engine, the current codebase is under migration and will continue. You will still find Blaze templates in our code. Code changes or contributions may need to be made in Blaze while we continue to evolve our components library.

The [Fuselage](https://github.com/RocketChat/Rocket.Chat.Fuselage) is our component library based on React, check it out when contributing to the Rocket.Chat UI and feel free to contribute new components or fixes.

### Standards

Most of the coding standards are covered by ESLint configured at [.eslintrc](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.eslintrc), and most of them came from our own [ESLint Config Package](https://github.com/RocketChat/eslint-config-rocketchat).

Things not covered by `eslint`:

* Prefer longer/descriptive variable names, e.g. `error` vs `err`, unless dealing with common record properties already shortened, e.g. `rid` and `uid`
* Use return early pattern. [See more](https://blog.timoxley.com/post/47041269194/avoid-else-return-early)
* Prefer `Promise` over `callbacks`
* Prefer `await` over `then/catch` (also valid for unit/e2e test callbacks)
* Don't create queries outside models, the query description should be inside the model class.
* Don't hardcode fields inside models. the same method can be used for different purposes, using different fields.
* Prefer to create REST endpoints over Meteor methods
* Prefer to call REST endpoints over Meteor methods when both are available
* v1 REST endpoints should follow the following pattern: `/api/v1/dashed-namespace.camelCaseAction`
* Prefer TypeScript over JavaScript. Check ECMAScript vs TypeScript

### Best practices

* Avoid "internal" `Meteor.call` - server code should not use `Meteor.call`

### Syntax check

Before submitting a PR you should get no errors on `eslint`.

To check your files run:

```
yarn lint
```

## Tests

There are 2 types of tests we run on Rocket.Chat, **Unit** tests, and **End to End** tests. The major difference is that End to End tests require a Rocket.Chat instance running to execute the API and UI checks.

### End to End Tests

First, you need to run a Rocket.Chat server on **Test Mode** and on an **Empty Database**:

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

### Unit Tests

Unit tests are simpler to set up and run. They do not require a working Rocket.Chat instance.

```
yarn testunit
```

It's possible to run on watch mode as well in the `apps/meteor` folder with:

```
yarn testunit-watch
```

## Before Push your code

It's important to run the lint and tests before pushing your code or submitting a Pull Request, otherwise, your contribution may fail quickly on the CI. Reviewers are forced to demand fixes and the review of your contribution will be further delayed.

Rocket.Chat uses [husky](https://www.npmjs.com/package/husky) to run the **lint** and **unit tests** before proceeding to the code push process, so you may notice a delay when pushing your code to your repository.

## Choosing a good PR title

It is very important to note that we use PR titles when creating our changelog. Keep this in mind when you title your PR. Make sure the title makes sense to a person reading a release's changelog!

Keep your PR's title as short and concise as possible, and use PR's description section, which you can find in the PR's template, to provide more details in the changelog.

Good titles require thinking from a user's point of view. Don't get technical and talk about code or architecture. What is the actual user-facing feature or the bug fixed? For example:

```
feat: Allow search permissions and settings by name instead of only ID
```

Even if it brings something new to the code the users already expect the filter to filter by what they see (translations), a better one would be:

```
fix: Permissions' search doesn't filter based on presented translation, only on internal ids
```

## Choosing the right PR tag

You can use several tags to describe your PR, i.e.: `fix:`, `feat:`, etc. You can use the descriptions below to better understand the meaning of each one, and decide which one you should use:

After the release of version `6.0.0` we adopted conventional commits plead check: [https://www.conventionalcommits.org/en/v1.0.0/#specification](https://www.conventionalcommits.org/en/v1.0.0/#specification)

You can use several tags to describe your PR, i.e.:

```json
feat|fix|ci|chore|docs|test|refactor|i18n|regression|revert
```

, etc. You can use the descriptions below to better understand the meaning of each one, and decide which one you should use:

### `feat:`

**When**

* When adding a new feature that is important to the end-user

**How**

Do not start repeating the section (`Add ...` , `New ...` or `Feature...`  Always describe what's being fixed, improved, or added and not _how_ it was fixed, improved, or added.

Examples of <mark style="color:red;">**bad**</mark> PR titles:

```
feat: Add the ability to set tags in the Omnichannel room closing dialog
feat: Adds the ability for Rocket.Chat Apps to create discussions
feat: Add MMS support to Voxtelesys
feat: Add Color variable to the left sidebar
```

Examples of <mark style="color:green;">**good**</mark> PR titles:

```
feat: Ability to set tags in the Omnichannel room closing dialog
feat: Ability for Rocket.Chat Apps to create discussions
feat: MMS support to Voxtelesys
feat: Color variable to the left sidebar
```

### `fix:`

**When**

* When fixing something not working or behaving wrong from the end-user perspective

**How**

Always describe what's being fixed and not _how_ it was fixed.

Example of a <mark style="color:red;">**bad**</mark> PR title:

```
fix: Add Content-Type for public files with JWT
```

Example of a <mark style="color:green;">**good**</mark> PR title:

```
fix: Missing Content-Type header for public files with JWT
```

### `chore:`

**When**

* For small tasks such as changing a function name or something very quickly that does not fit in another category.

**How**

Always describe what's being changed and not _how_ it was changed.

Example of a <mark style="color:red;">**bad**</mark> PR title:\[IMPROVE] Displays Nothing found on admin sidebar when a search returns nothing

```
chore: Renaming `getNewMessage` function and replacing it in all files that use this function
```

Example of a <mark style="color:green;">**good**</mark> PR title:

```
chore: Rename `getNewMessage` function
```

### `docs:`

**When**

* For documentation such as `README.md` files, and other markdown and instruction files that bring value to the community

**How**

Always describe what's being changed and not _how_ it was changed.

Example of a <mark style="color:green;">**good**</mark> PR title:

```
docs: Update Pull Request Template
```

### `refactor:`

**When**

* A code refactor that doesn't change behavior (it doesn't add anything and doesn't fix anything) such as: converting javascript file to typescript

Examples of <mark style="color:green;">**good**</mark> PR titles:

```
refactor: RoomInfo to typescript
```

### `ci:`

**When**

* A change that updates or adds a CI configuration

Examples of <mark style="color:green;">**good**</mark> PR titles:Fix: Missing Content-Type header for public files with JWT

```
ci: PR title check to use conventional commits
```

### `test:`

**When**

* For adding tests

Examples of <mark style="color:green;">**good**</mark> PR titles:

```
test: RoomInfo e2e tests
```

### `i18n:`

**When**

* For updating or adding any translations

Examples of <mark style="color:green;">**good**</mark> PR titles:

```
i18n: Homepage translations to pt-BR
```

### `regression:`

**When**

* When changes are made during any release candidate cycle, in order to add something missing or fix something broken during the last development cycle and _not published to a final release yet_.

Examples of <mark style="color:green;">**good**</mark> PR titles:

```
regression: Fix not being able to mark room as read 
regression: Add missing field to `users` endpoint
```

## Security Best Practices

* Never expose unnecessary data to the APIs' responses
* Always check for permissions or create new ones when you must expose sensitive data
* Never provide new APIs without rate limiters
* Always escape the user's input when rendering data
* Always limit the user's input size on the server-side
* Always execute the validations on the server-side even when executing on the client-side as well

## Performance Best Practices

* Prefer to inform the fields you want, and only the necessary ones, when querying data from the database over query the full documents
* Limit the number of returned records to a reasonable value
* Check if the query is using indexes, if it's not, create new indexes
* Prefer queues over long executions
* Create new metrics to measure things whenever possible
* Cache data and returns whenever possible

## Contributor License Agreement

To have your contribution accepted you must sign our [Contributor License Agreement](https://cla-assistant.io/RocketChat/Rocket.Chat). In case you submit a Pull Request before signing the CLA GitHub will alert you with a new comment asking you to sign and will block the Pull Request from being merged by us.

Please review and sign our CLA at [https://cla-assistant.io/RocketChat/Rocket.Chat](https://cla-assistant.io/RocketChat/Rocket.Chat)
