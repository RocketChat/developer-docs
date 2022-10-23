# Publishing a new release



**Before starting publishing a new release, make sure to test the latest development branch in Rocket.Chat to check and prevent possible issues.**

First of all, you need to have `GH_TOKEN` environment variable set in your terminal:

> GH\_TOKEN (required) - Your GitHub authentication token (under Settings > Developer settings > Personal access tokens).

```bash
export GH_TOKEN=... # your token
```

```bash
git checkout master
```

```bash
git pull origin master
```

Merge with develop without [fast forward](https://i.stack.imgur.com/rTxx9.png):

```bash
git merge --no-ff origin/develop
```

Make sure to run yarn to ensure all packages are properly installed:

```bash
yarn 
```

_Optional step to verify changes with flag `dry-run`:_

```bash
yarn bump --commit --tag --dry-run
```

Bumps and verifies new current version based on last commits, using [npm standard-version](https://www.npmjs.com/package/standard-version)

```bash
yarn bump --commit --tag
```

_Optional step to check if the latest commit is the core commit related to the release:_

```bash
git log
```

Push to origin (remote):

```bash
git push --follow-tags
```

Steps to merge branch master into develop:

```bash
git checkout develop
git pull origin develop
git merge master --no-ff
git push
```
