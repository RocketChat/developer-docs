# Monorepo

### Overview

The word _Fuselage_ has three distinct meanings on Rocket.Chat:

* The [design system](https://uxdesign.cc/everything-you-need-to-know-about-design-systems-54b109851969) for all Rocket.Chat projects;
* The set of components and assets that make up the design system;
* The name of the [monorepo](https://en.wikipedia.org/wiki/Monorepo) that contains all of the above (and a bunch of other stuff).

In order to avoid confusion, we will refer to the _Fuselage_ monorepo as the _Fuselage Monorepo_.

#### Why a monorepo?

FromFrom the very beginning, the Rocket.Chat project embraced the idea of splitting the codebase into multiple packages, as the Meteor community has done. It was a way to separate the codebase into smaller pieces from feature point of view, and to make it easier to work on them. This approach was successful specially when some dependencies became stale and were not updated.

Interdependencies between packages is a maintenance issue, and it is not easy to find a way to keep everything in sync when you have multiple repositories. Naturally, the [Rocket.Chat repository](https://github.com/RocketChat/Rocket.Chat) became a monorepo managed by Meteor (but no one really knew it). Then everything changed when ~~the Fire Nation attacked~~ server scalability issues started to appear, and a "de-meteorization" of the codebase was needed. At the time this is written, less than ten of Meteor packages remain in the Rocket.Chat repository.

The _Fuselage Monorepo_ was, initially, an attempt to fill the gap left by the old packages while introducing the design system implementation as a separate thing. The success of it can be seen by what "bunch of other stuff" is in the repository: it went beyond the components and assets and now contains all kind of package useful for frontend development.
