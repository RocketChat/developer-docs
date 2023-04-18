# Mac OSX

\
You can set up and run a Rocket.Chat development environment on your Mac OSX.

## Apple Silicon (M1/M2)

{% hint style="info" %}
* Node.js only has prebuilt binaries for [Apple Silicon](https://www.macworld.com/article/334279/apple-silicon-macs-may-be-a-reboot-of-the-g4-cube-and-colorful-imac-g3.html) as from `node v16`
{% endhint %}

* Install node with [nvm](https://github.com/nvm-sh/nvm). Make sure the nvm version is >= 0.39.2
* Install the required nodejs version using nvm. You can check the current required version in the `package.json` file [here](https://github.com/RocketChat/Rocket.Chat/blob/develop/package.json#L42-L46).

> For Apple Silicon, nvm (>= 0.39.2) will build nodejs from source if there is no official binary the needed version.

* Install yarn - read yarn's official documentation on [how to install yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable).
* Install Meteor - read the official documentation on [how to install Meteor](https://docs.meteor.com/install.html).
* Fork and clone the [Rocket.Chat repository](https://github.com/RocketChat/Rocket.Chat) and navigate into the directory

```shell
git clone https://github.com/your-username/Rocket.Chat
cd Rocket.Chat
```

* Run the following commands to navigate to the `meteor` directory to install the needed toolset, as configured in `.meteor/release` file

```shell
cd apps/meteor
meteor --version
```

* Go back to the project root (`cd -`). Build and start your development server by executing

```shell
yarn build
yarn dev # or yarn dsv if your system has less than 16 gigs of memory
```

> If you face any issues, see the [troubleshoot](mac-osx.md#troubleshooting) section.

When done, you should see the following printed on your terminal and the local server running on `http://localhost:3000`

![Rocket.Chat server successfully running on MacOSX](<../../../.gitbook/assets/image (51) (2).png>)

## Intel Chips

{% hint style="info" %}
This setup instruction has been tested on MacBook Pro 2015, 8Gig Ram, 512Gb SSD,i5
{% endhint %}

* Install Meteor by executing:

```
curl https://install.meteor.com/ | sh
```

Meteor comes pre-installed with npm and node. Verify by executing:

```
meteor node -v
meteor npm -v
```

* Install Yarn if you don't already have it on your system. Yarn is the recommended package manager

```
npm install --global yarn
```

{% hint style="success" %}
Information on the various versions of packages needed can be found in the `package.json`
{% endhint %}

* To easily manage the node versions on your machine, install the [n node package manager](https://www.npmjs.com/package/n) and switch to the desired node version you want to use

```
npm install -g n
n 14.21.1
node -v
```

* Fork and clone the Rocket.Chat repository [https://github.com/RocketChat/Rocket.Chat](https://github.com/RocketChat/Rocket.Chat) and navigate into the directory

```
git clone https://github.com/your-username/Rocket.Chat
cd Rocket.Chat
```

* Run the following commands to navigate to the `meteor` directory and download the necessary meteor version for Rocket.Chat, as configured in `.meteor/release` file

```
cd apps/meteor
meteor --version
```

* Back in the main directory, install all the packages by simply running

```
yarn
```

* Build and startup your development server by executing

```
yarn build
yarn dev
```

When done, you should see the following printed on your terminal and the local server running on `http://localhost:3000`

![Rocket.Chat server successfully running on MacOSX](<../../../.gitbook/assets/image (51) (2).png>)

## Troubleshooting

### 1. Command yarn failed with code 127 (Mac M1/2)

If you face an error like the following

```
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 127, logs can be found here: /private/var/folders/pq/xv5hx2d117jfxls2nx49wgrm0000gn/T/xfs-e2bec7de/build.log)
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 127, logs can be found here: /private/var/folders/pq/xv5hx2d117jfxls2nx49wgrm0000gn/T/xfs-08c5a85c/build.log)
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 127, logs can be found here: /private/var/folders/pq/xv5hx2d117jfxls2nx49wgrm0000gn/T/xfs-c7fa7b08/build.log)
```

Run this command before running `yarn` again

```shell
ln -sf $(which node) $(dirname $(which node))/nodejs
```

### 2. Fibers link failed (Mac M1/2)

If `yarn` is failing on the link step for fibers with a log similar to

```
➤ YN0007: │ fibers@npm:5.0.3 must be built because it never has been before or the last one failed
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 1, logs can be found here: /private/var/folders/pq/xv5hx2d117jfxls2nx49wgrm0000gn/T/xfs-7a9d15f1/build.log)
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 1, logs can be found here: /private/var/folders/pq/xv5hx2d117jfxls2nx49wgrm0000gn/T/xfs-b359748c/build.log)
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 1, logs can be found here: /private/var/folders/pq/xv5hx2d117jfxls2nx49wgrm0000gn/T/xfs-62becf57/build.log)

```

Install `node-gyp` globally

```shell
npm install node-gyp --global
```

Rebuild fibers for the system architecture manually

```shell
cd node_modules/fibers && node-gyp rebuild --arch=arm64
```

Move the binary to the correct location

```shell
mkdir bin/darwin-arm64-83
cp build/Release/fibers.node bin/darwin-arm64-83/fibers.node
```

Share the directory

```shell
cd ../../ && cp -r node_modules/fibers apps/meteor/node_modules/
```

### 3. Bcrypt requires arm64 binary but has amd64 one (Mac M1/2)

The error specifically looks like the following

```
(mach-o file, but is an incompatible architecture (have 'x86_64', need 'arm64e')), '/usr/local/lib/bcrypt_lib.node' (no such file), '/usr/lib/bcrypt_lib.node' (no such file)
```

Move to the bcrypt directory and rebuild everything

```shell
cd node_modules/bcrypt && make
```

Once the build is successful, share the module

```shell
cd ../.. && cp -r node_modules/bcrypt apps/meteor/node_modules/
```
