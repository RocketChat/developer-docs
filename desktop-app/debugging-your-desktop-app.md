# Debugging your Desktop App

In this development phase, you'll dive into troubleshooting techniques to ensure your application functions seamlessly. Here, you'll find valuable insights and strategies to identify, isolate, and rectify issues that may arise during the development process.

### Troubleshooting

**node-gyp**

{% hint style="info" %}
Follow the installation instructions on [node-gyp README](https://github.com/nodejs/node-gyp).
{% endhint %}

If you encounter package failures, it is advisable to conduct a thorough cross-check to ensure that the specified packages are readily available within your environment.

{% tabs %}
{% tab title="Windows" %}
For Windows users, it might be necessary to refer to the [second option outlined in the node-gyp installation guide](https://github.com/nodejs/node-gyp#on-windows), which involves installing Visual Studio.
{% endtab %}

{% tab title="MacOS" %}
Additionally, installing [`Xcode Command Line Tools`](https://developer.apple.com/xcode/) is essential. To install, run this command:

```
xcode-select --install
```

Alternatively, if you already have the full Xcode installed, navigate to **Xcode -> Open Developer Tool -> More Developer Tools** to get it. This step will install `clang`, `clang++`, and `make`.
{% endtab %}

{% tab title="Ubuntu" %}








1. `build-essential`
2. `libevas-dev`
3. `libxss-dev`
{% endtab %}

{% tab title="Fedora" %}
Your project may require these additional packages:

1. `libX11`
2. `libXScrnSaver-devel`
3. `gcc-c++`d
{% endtab %}
{% endtabs %}
