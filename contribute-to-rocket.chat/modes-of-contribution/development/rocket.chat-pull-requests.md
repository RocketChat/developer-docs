# Rocket.Chat Pull Requests

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
