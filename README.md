# AwayFL Template
Template project for AwayFL Player

## Prerequistes ##
 - git ([installation instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git))
 - Node.js ([installation instructions](https://nodejs.dev/learn/how-to-install-nodejs))

## Installing ##
Click the 'Use this template' button and follow the instructions to create a copy of the template in your own repository. Then checkout and install a local copy in the usual way by typing the following into a terminal / cmd prompt / shell window:
```shell
git clone https://github.com/myorg/myconversionproject
cd myconversionproject
npm install
```

## Naming conventions ##
By default, your project name is `awayfl-template`. You can change this by opening `./package.json` and editing the `"name"` entry. You should also update the name visible in `./src/Main.ts` as this will be used to keep track of releases when publishing. Be sure to keep the `0.0.0` number at the end of the name as this is used to auto-increment version numbers.

## Configuration ##
Open the `awayfl.config.js` file and add some SWF files to `fileconfigs`, including a `rt_title` and `rt_filename` entry (without the .swf extension), eg:
```javascript
fileconfigs: [
    {
        rt_title: "my Awesome Flash Game",
        rt_filename: "my_awesome_flash_game",
    },
],
```
`awayfl.config.js` contains many additional configs (documented inline) that can be applied either global or locally to individual test SWFs.

## Preview ##
To run a preview of your SWFs, start up the webpack development server
```shell
npm start
```
Once compilation is complete, you can view your SWFs through the links at http://localhost. Updating SWFs or any files in  `/src` will auto-reload the browser. However, any changes to `awayfl.config.js` will require a restart.

## Publishing ##
Once you are ready to publish a version of your game(s) for QA, you can create a new version by calling the following:
```shell
npm version patch
```
This automatically increments the version number, as well as building a local copy of your published files in the temporary `./bin` folder. The published files have the following structure:

 - game_name_1
   - /assets
   - /js
   - index.html
 - game_name_2
   - /assets
   - /js
   - index.html
 - ...

Each folder contains the source, swfs and support files to allow the publishing of individual games with accompanying AwayFL files as a standalone distributable.
