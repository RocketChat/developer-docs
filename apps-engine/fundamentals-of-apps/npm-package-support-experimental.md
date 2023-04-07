# NPM Package Support (Experimental)

As of Apps-Engine v1.28.0 (released in Rocket.Chat v4.0), Rocket.Chat Apps include a subset of NPM packages as dependencies to be used at runtime. While we could not determine the list of all packages that are supported (due to the sheer amount of options available), based on the technical constraints of our implementation, we know that:

{% hint style="warning" %}
**Note:** when using NPM packages in your app, make sure to use the latest `rc-apps` version (v1.10.1 at the time of this writing) - it is responsible for bundling the code of the packages along with the app's source code
{% endhint %}

* Utility packages that are **not** dependent on NodeJS' native modules **should** definitely work (e.g. lodash, momentjs, etc);
* Packages that create any type of server, be it HTTP, TCP, UDP, or IPC, **will not** work (e.g. express, hapi, etc);
* Packages that interact with the `fs` and `os` modules **will not** work;

If you try using a package that should work but isn't, open an issue in the [Rocket.Chat.Apps-engine repository ](https://github.com/RocketChat/Rocket.Chat.Apps-engine)and we'll check it out!
