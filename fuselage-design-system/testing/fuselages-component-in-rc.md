---
description: Test fuselage component/packages in Rocket.Chat main repository
---

# Fuselage's component in RC

These are some techniques applied when we need to iterate over some components and/or packages in use at our flagship project and Storybook or local environment it's not enought.

All the examples assume the work tree directories are siblings disposed like this:

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

## Technique 1: `yarn fuselage` script&#x20;

We developed a helper script to automate actions needed to test and deploy fuselage packages.

The bash script source code can be found here: [fuselage.sh](https://github.com/RocketChat/Rocket.Chat/blob/develop/fuselage.sh)

The script can be used with the `yarn fuselage -a [action] -p [package]` command

The actions are specified with the flag  `-a | --action` and the options are `[link|undo|unlink|next|latest|next-all|latest-all]`&#x20;

* &#x20;`link` : Creates a symbolic link for the fuselage package&#x20;
* &#x20;`undo` or `unlink` : Removes the symbolic li nk for the fuselage package&#x20;
* &#x20;`next` : Update dependencies with the @next npm package version&#x20;
* &#x20;`latest` : Update dependencies with the @latest npm package version&#x20;
* &#x20;`next-all` : Update ALL fuselage dependencies with the @next npm packages version&#x20;
* &#x20;`latest-all` : Update ALL fuselage dependencies with the @latest npm packages version

The packages that the action will be performed it's specified with `-p | --package`  flag, this option can contain multiple packages separated by a semicolon (;) like `[package1;package2]`

Example usage:

* Create a symbolic link in multiple fuselage packages:

```bash
yarn fuselage -a link -p fuselage;fuselage-icons;message-parser
```

* Remove the symbolic link:&#x20;

```bash
yarn fuselage -a undo
```

* Update dependencies to the @rocket.chat/fuselage@next npm package version:

```bash
 yarn fuselage -a next -p fuselage
```

* Update dependencies to the @rocket.chat/fuselage@latest npm package version:

```bash
 yarn fuselage -a latest -p fuselage
```

* Update ALL fuselage dependencies with the @next npm packages version:

```bash
 yarn fuselage -a next-all
```

* Update ALL fuselage dependencies with the @latest npm packages version:&#x20;

```bash
yarn fuselage -a latest-all
```



## Technique 2: Yarn's `link:` protocol

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

## Technique 3: Already merged PR

Usually, the versions kept on the core package (Rocket.Chat) are set to `@next`. This means that merged PR's that were merged to develop and went through the CI/CD (usually takes a few minutes after merge) are released as a `-dev` version.

In order to find out if a merged PR has already been released, in the fuselage monorepo, go to `Actions` and find `Continuous Delivery` in the sidebar. Now search for your PR's title and if the action has finished running, you're ready to got to the next step:

#### On Core repository root, run:

Update fuselage packages to `@next`

```bash
yarn up @rocket.chat/fuselage@next
```

After this runs, make sure to run:

```bash
yarn build
```

And you're ready to go!

## Technique 4: Before the Fuselage Pull Request is merged

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
