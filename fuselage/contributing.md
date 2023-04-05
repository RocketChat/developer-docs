# Contributing

## Starting from the beginning

To start the development you need to clone the project.

```bash
$ git clone git@github.com:RocketChat/Rocket.Chat.Fuselage.git
```

Then, if you browse packages you will notice that there are several packages within the same repository.

```bash
cd Rocket.Chat.Fuselage/packages/
ls
# css-in-js          
# emitter
# fuselage
# fuselage-emitter
# fuselage-hooks
# fuselage-polyfills
# fuselage-tokens
# fuselage-ui-kit
# icons
# memo
# mp3-encoder
# ui-kit
```

## How to build your project

```bash
# at root folder
yarn && yarn build
```

## How to develop and test under Rocket.Chat the local code

It's pretty easy, inside Rocket.Chat project just run:

```bash
 meteor npm i ${paht_to_fuselage_folder}/packages/package
```

## How not to fail your pull request

The fuselage package is covered by visual regression tests. So, if you are changing any component, if there is any desired visual change, don't forget to update the images. Docker is required for that step.

{% code title="packages/fuselage" %}
```bash
yarn update-storybook
```
{% endcode %}

If you are creating something new, be sure to create a story for the component, it will not fail the pull request, but it will probably not be approved or even considered ready for review.

## My pull request was merged, what now?

As soon as your contribution gets accepted, approved, and merged it will start the build process, even if your **PR** is only merged on develop. After that, the package will be available at **npm** tagged as **@next**. With that, you can already work/open pull requests on Rocket.Chat. At the end of Rocket.Chat release, we will release a fuselage production version and update the fuselage packages on Rocket.Chat.
