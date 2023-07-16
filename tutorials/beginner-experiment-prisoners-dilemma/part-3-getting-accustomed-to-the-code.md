# Part 3: Getting Accustomed to the Code

To get a glimpse of the actual code that runs Empirica, open Visual Studio Code to the `deliberation-empirica` folder.&#x20;

> You can either do this manually, by going to `File > Open Folder` and selecting the `deliberation-empirica` folder, or by typing in your terminal `code .` within the `deliberation-empirica` directory.

The template experiment includes three subdirectories:

1. `.empirica`  stores data and config files that we need to run the experiment.
2. `client`  is where the code that runs on your experiment participant's browser lives.
3. `server` is where all the code that runs on the server lives.

<figure><img src="../../.gitbook/assets/Screenshot 2023-06-09 at 2.48.04 AM.png" alt="" width="354"><figcaption><p>Collapsed File Tree</p></figcaption></figure>

The `client` and `server` directories are each structured as a node package, and contain some boilerplate code that we can ignore:

* `node_modules/` is a folder containing dependencies, and is managed for us (we never need to touch it)
* `dist/` is a folder for the compiled version of our code, which gets built automatically
* `package.json` and `package-lock.json` contain references to other packages that our experiment depends on
* `client/index.html`, `client/vite.config.js`, `client/uno.config.ts`, `client/jsconfig.json` `server/jsconfig.js` are all configuration files we can leave as they are

In this tutorial, we will make changes in the following places:

* `client/src/` is a folder containing the views the participant sees, built up as React components.
* `server/src/callbacks.js` is a file for server-side code that is called when specific actions happen in the game.
* `.empirica/local/tajriba.json` is where our experiment data is stored. It is often helpful to delete this file when you restart the server, to start with a clean slate.&#x20;

Have a quick browse through the files in `client/src/examples` to see how the jelly bean and minesweeper examples are implemented.
