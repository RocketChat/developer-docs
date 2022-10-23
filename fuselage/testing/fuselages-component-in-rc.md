# Fuselage's component in RC

These are some techniques applied when we need to iterate over some components in use at our flagship project and Storybook is not enough.

All the examples assume the worktree directories are siblings disposed like this:

```
- fuselage
  - .git
  - packages
    - ...on
  - ...
- Rocket.Chat
  - .git
  - apps
    - meteor
      - ...
    - ...
  - ...
```

## Technique 1: Yarn's `link:` protocol

### Do

Run `webpack` in watch mode on `@rocket.chat/fuselage`:

```bash
cd fuselage/packages/fuselage
yarn start
cd -
```

Add a relative-path link resolution for `@rocket.chat/fuselage` on the root `package.json`:

```json
// Rocket.Chat/package.json
{
  // ...
  "resolutions": {
    // ...
    "@rocket.chat/fuselage": "link:../fuselage/packages/fuselage"
  }
}
```

Update `yarn.lock`:

```bash
cd Rocket.Chat
yarn
cd -
```

### Undo

To undo the link when your work is done:

```bash
cd Rocket.Chat
yarn unlink --all ../fuselage
cd -
```

#### Notes

<details>

<summary>Why not use `yarn link`?</summary>

Usually, the same result could be achieved through the `yarn link` command, but it appears that Yarn prefers the `portal:` protocol ([source](https://yarnpkg.com/features/protocols)) and it's not suited for this usage as some dependencies between the worktrees collide:

```
yarn link ../fuselage/packages/fuselage                                                                                                                                                                                    26581ms 
➤ YN0000: ┌ Resolution step
➤ YN0001: │ Error: @rocket.chat/css-in-js@workspace:~: Workspace not found (@rocket.chat/css-in-js@workspace:~)
    at ze.getWorkspaceByDescriptor (/Users/tasso/Projetos/Rocket.Chat/.yarn/releases/yarn-3.2.0.cjs:441:3273)
    at md.getCandidates (/Users/tasso/Projetos/Rocket.Chat/.yarn/releases/yarn-3.2.0.cjs:394:29907)
    at wd.getCandidates (/Users/tasso/Projetos/Rocket.Chat/.yarn/releases/yarn-3.2.0.cjs:395:1281)
    at wd.getCandidates (/Users/tasso/Projetos/Rocket.Chat/.yarn/releases/yarn-3.2.0.cjs:395:1281)
    at /Users/tasso/Projetos/Rocket.Chat/.yarn/releases/yarn-3.2.0.cjs:441:7765
    at Pg (/Users/tasso/Projetos/Rocket.Chat/.yarn/releases/yarn-3.2.0.cjs:394:11098)
    at le (/Users/tasso/Projetos/Rocket.Chat/.yarn/releases/yarn-3.2.0.cjs:441:7745)
➤ YN0000: └ Completed in 0s 391ms
➤ YN0000: Failed with errors in 0s 398ms
```

</details>

## Technique 2: Already merged PR

Usually, the versions kept on the core package (Rocket.Chat) are set to `@next`. This means that merged PR's that were merged to develop and went through the CI/CD (usually takes a few minutes after merge) are released as a `-dev` version. Unfortunately, running `yarn install` doesn't always update packages set to @next. This means that to test this new version, the following has to be done.

#### On Core repository root, run:

Clean 'node\_modules' and 'yarn.lock':

```bash
find . -name 'node_modules' -type d -prune -exec rm -rf '{}' +
```

```bash
rm -rf ./yarn.lock
```

Clean yarn cache:

```bash
yarn cache clean --all
```

Install packages and build modules:

```bash
yarn && yarn build
```

It may take some extra time but ensures the package installed will be the correct, newer version.

## Technique 3: Before the Fuselage Pull Request is merged

If you want to test your `fuselage/{package}` code in [Rocket.Chat main repository](https://github.com/RocketChat/Rocket.Chat) you can also use this technique: create a symbolic link (symlink) to a `fuselage/{package}` at Rocket.Chat main repository.

#### On Core repository root, run:

1. Install dependencies and build packages:

```bash
yarn && yarn build
```

1. Create a symlink to `fuselage/{package}` at meteor `node_modules`

```bash
yarn && yarn build
cd apps/meteor/node_modules/@rocket.chat # To find meteor node_modules/@rocket.chat directory where the fuselage packages are installed
rm -rf {package} # Where {package} is the name of fuselage package, e.g: fuselage, message-parser, ui-kit, icons and others...
ln -s ../../../../../fuselage/packages/{package} ./{package} # Where {package} is the name of fuselage package and the path needs to aligned to your project location
```

1. Go back to main repository root and start the server:

```bash
yarn dev
```

> :warning: Be careful when running `yarn dsv` to start only the **meteor** project because the desired package could be used by other packages besides **meteor** and could impact the outcome

After this steps you should be able to see the changes in your application.
