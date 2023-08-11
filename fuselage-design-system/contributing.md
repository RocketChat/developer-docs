# Contributing

At Rocket.Chat, we believe that great softwares are built through collaboration and the collective efforts of a vibrant community. We're thrilled to welcome you to the Rocket.Chat Fuselage repository, where we develop the UI component library that powers the user interfaces of Rocket.Chat applications. Whether you're a seasoned developer or just starting your coding journey, your contributions play a crucial role in shaping the future of our open-source project.

To contribute to the Fuselage Monorepo, follow these guidelines:

1. Clone the [GitHub repository](https://github.com/RocketChat/fuselage/) with this command:

```
git clone git@github.com:RocketChat/Rocket.Chat.Fuselage.git
```

2. Navigate to the _packages_ directory to see the several existing packages.

```
cd fuselage/packages/
ls
```

3. Run this command  at the root directory to build your project:

```bash
yarn && yarn build
```

4. To **develop and test the local code** in the Rocket.Chat project, run this command:

```
 meteor npm i ${path_to_fuselage_folder}/packages/package
```

#### **Creating Pull Requests**

The fuselage package uses visual regression tests to ensure that the visual appearance of the package does not change when code is changed. If you make a change to a component in the fuselage package that results in a visual change, you must also update the images that are used in the visual regression tests. This ensures that the visual regression tests will continue to pass after your changes have been made.

* To update the storybook, navigate to _packages/fuselage_ and run this command:

{% code title="packages/fuselage" %}
```bash
yarn update-storybook
```
{% endcode %}

{% hint style="warning" %}
If you are creating a new component, you should create a story for it. This is not required, but it is highly recommended. Without a story, your pull request will likely not be approved or even considered ready for review.
{% endhint %}

**Merged Pull Request**

Congratulations on getting your pull request merged! That's a great accomplishment.

Here are the next steps:

* The build process will start immediately, even if your PR was only merged on the `develop` branch. This will create a new version of the fuselage package that is tagged as `@next`.
* The `@next` version of the fuselage package will be available on npm. You can use this version to work on pull requests for Rocket.Chat.
* At the end of the Rocket.Chat release, a new production version of the fuselage package will be released. The fuselage packages on Rocket.Chat will be updated to the new production version.

Your remarkable contributions to the fuselage package are deeply appreciated. You are encouraged to work on new features and bug fixes for the fuselage package. Let's continue this journey of improvement together!
