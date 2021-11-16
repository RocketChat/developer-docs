# Debugging your Desktop App

## Troubleshooting

### **node-gyp**

Follow the installation instructions on [node-gyp README](https://github.com/nodejs/node-gyp).

In case of any package failures, cross-check or better still make sure you have these packages available on your environment.

{% tabs %}
{% tab title="Windows" %}
On Windows you may have to follow [option 2 of the node-gyp install guide](https://github.com/nodejs/node-gyp#on-windows) and install Visual Studio.
{% endtab %}

{% tab title="MacOS" %}

{% endtab %}

{% tab title="Ubuntu" %}
1. `build-essential`
2. `libevas-dev`
3. `libxss-dev`
{% endtab %}

{% tab title="Fedora" %}
1. `libX11`
2. `libXScrnSaver-devel`
3. `gcc-c++`d
{% endtab %}
{% endtabs %}
