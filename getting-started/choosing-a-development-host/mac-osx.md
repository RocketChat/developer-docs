# Mac OSX

You can run Rocket.Chat for development on  Mac OSX. The following instructions has been tested on  M1 Macs.

1. Install Meteor 

    Currently Meteor don’t support Apple M1 native binaries as the latest meteor release uses Node.js 14 which doesn’t have support for it until now.

    You can use Rosetta and enter the below command.

    `arch -x86_64 npm install -g meteor`

    or select Terminal in the Applications folder, press CMD(⌘)+I and check the “Open using Rosetta” option then using this command.

    `npm install -g meteor`

    (If your user doesn’t have permission to install global binaries, and you need to use sudo, it’s necessary to append –unsafe-perm to the below command:
     `sudo npm install -g meteor --unsafe-perm` )
     
      There is no need to install `node` or `npm`, as meteor already includes them. Verify by:
      
      `meteor node -v`
      
      `meteor npm -v`

   
2) Fork the repository ` https://github.com/RocketChat/Rocket.Chat.git` and then clone the forked repository in your system.

3) Install Modules

    `cd Rocket.Chat`

    `meteor npm install`

4) Start building \(the first build can _take 10 or more minutes_, and you may see various warnings or minor errors -- please be patient; subsequent dev builds after the first will be 5 minutes or less\)

   `meteor npm start`

When the server is ready, you will see a box with "Server Running" title:


This means that a Rocket.Chat server is running from your computer. To access the server, navigate to

`http://localhost:3000`

If you face any error like `npm ERR! Failed at the sharp@0.22.1 install script.` while installing modules.

```
1) Delete node_modules folder and package-lock.json
2) Install sharp first (If it still throws an error lower you node version to v12 and
   install sharp then back to same node version)
3) meteor npm install
4) meteror npm start
  (It might prompt you to do npm rebuild if you used lower version of node to install sharp. Do the rebuild
  and then meteor npm start)
```

### Editing Rocket.Chat Files

Editing files is relatively simple. After you run `git clone`, the files from the repository are saved on your computer. You can go to the cloned repository folder and edit or add files to Rocket.Chat. When you make changes to Rocket.Chat the server will automatically rebuild.

Sometimes changes can shut down the server, if that happens just run `meteor npm start` again.

The Rocket.Chat code base is very large. You may need to increase this [system parameter ](https://github.com/meteor/docs/blob/master/long-form/file-change-watcher-efficiency.md)on your operating system for the files-change watcher to operate efficiently.

Other references:

* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Meteor](https://www.meteor.com/install)
