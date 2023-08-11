---
description: Test fuselage component/packages in Rocket.Chat main repository
---

# Fuselage's component in RC

There are several techniques employed when the necessity arises to iterate through components or packages being used in our flagship project. In cases where Storybook or the local environment proves insufficient, the following approaches are implemented. It is important to note that all examples assume a directory structure where the work tree directories are organized as siblings, as illustrated below:

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

This configuration serves as the foundation for the following techniques.

### Technique 1: `yarn fuselage` script&#x20;

We've created a convenient helper script to streamline the testing and deployment process for Fuselage packages. The source code of this bash script can be accessed at [fuselage.sh](https://github.com/RocketChat/Rocket.Chat/blob/develop/fuselage.sh) directory.

This script is designed to be utilized using the command `yarn fuselage -a [action] -p [package]`, offering a flexible way to perform various actions. Actions are specified using the `-a | --action` flag, and the available options are: `[link|undo|unlink|next|latest|next-all|latest-all]`.

* &#x20;`link` : Creates a symbolic link for the fuselage package&#x20;
* &#x20;`undo` or `unlink` : Removes the symbolic li nk for the fuselage package&#x20;
* &#x20;`next` : Update dependencies with the @next npm package version&#x20;
* &#x20;`latest` : Update dependencies with the @latest npm package version&#x20;
* &#x20;`next-all` : Update ALL fuselage dependencies with the @next npm packages version&#x20;
* &#x20;`latest-all` : Update ALL fuselage dependencies with the @latest npm packages version

The packages that the action will be performed it's specified with `-p | --package`  flag, this option can contain multiple packages separated by a semicolon (;) like `[package1;package2]`

**Example usage**

* Create a symbolic link in multiple fuselage packages using this command:

```bash
yarn fuselage -a link -p fuselage;fuselage-icons;message-parser
```

* Remove the symbolic link with this command:&#x20;

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

* Update **ALL** fuselage dependencies with the @next npm packages version:

```bash
 yarn fuselage -a next-all
```

* Update **ALL** fuselage dependencies with the @latest npm packages version:&#x20;

```bash
yarn fuselage -a latest-all
```

### Technique 2: Yarn's `link:` protocol

**Add a link**

* Run `webpack` in watch mode on `@rocket.chat/fuselage`:

```bash
cd fuselage/packages/fuselage
yarn start
cd -
```

* Add a relative-path link resolution for `@rocket.chat/fuselage` on the root `package.json`:

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

* Update `yarn.lock`:

```bash
cd Rocket.Chat
yarn
cd -
```

**Undo the link**

* Run the following commands:

```bash
cd Rocket.Chat
yarn unlink --all ../fuselage
cd -
```



<details>

<summary>Why not use `yarn link`?</summary>

While the `yarn link` command typically achieves the desired outcome, Yarn seems to favor the "portal:" [protocol](https://yarnpkg.com/features/protocols), which can lead to dependency conflicts between worktrees. This preference poses limitations, making it unsuitable for this particular use case.

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

### Technique 3: Already merged PR

Usually, the versions kept on the core package (Rocket.Chat) are set to `@next`. This means that merged PR's that were merged to develop and went through the CI/CD (usually takes a few minutes after merge) are released as a `-dev` version.

To determine whether a merged PR has been released, follow these steps within the Fuselage monorepo:

1. Navigate to the "Actions" tab and access "Continuous Delivery" from the sidebar.
2. Search for your PR's title. If the action has finished running, follow these next steps:

* In the [Rocket.Chat repository](https://github.com/RocketChat/Rocket.Chat) root directory, update fuselage packages to `@next` with this command:

```bash
yarn up @rocket.chat/fuselage@next
```

* Then, build the project with this command:

```bash
yarn build
```

You're now set to proceed.

### Technique 4: Before the Fuselage Pull Request is merged

To test your Fuselage package code within the [Rocket.Chat main repository](https://github.com/RocketChat/Rocket.Chat), you can use this technique. Create a symbolic link (symlink) pointing to the corresponding `fuselage/{package}` directory within the Rocket.Chat repository.

* In the [Rocket.Chat repository](https://github.com/RocketChat/Rocket.Chat) root directory, run this command to install dependencies and build packages:

```bash
yarn && yarn build
```

* Create a symlink to `fuselage/{package}` at meteor `node_modules`with this command:

```bash
yarn && yarn build
cd apps/meteor/node_modules/@rocket.chat # To find meteor node_modules/@rocket.chat directory where the fuselage packages are installed
rm -rf {package} # Where {package} is the name of fuselage package, e.g: fuselage, message-parser, ui-kit, icons and others...
ln -s ../../../../../fuselage/packages/{package} ./{package} # Where {package} is the name of fuselage package and the path needs to aligned to your project location
```

* Navigate back to the main repository root and start the server:

```bash
yarn dev
```

{% hint style="warning" %}
Exercise caution when using the `yarn dsv` command to start the Meteor project. It's important to note that the intended package might be utilized by other packages beyond Meteor, potentially affecting the overall result.
{% endhint %}

After following these steps, your application should reflect the changes.
