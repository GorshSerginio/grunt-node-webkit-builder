# grunt-node-webkit-builder

> Let's you build your node-webkit apps for mac, win and linux with grunt. It will download the prebuilt binaries for a specify version, unpacks it, creates a release folder, create the app.nw file for a specified directory and copys the app.nw file where it belongs.

## Getting Started
This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-node-webkit-builder --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-node-webkit-builder');
```

## The "nodewebkit" task


### Options

#### options.version
Type: `String`
Default value: `'0.7.0'`

The version of node-webkit you want to use. [Here is a list](https://github.com/rogerwang/node-webkit/wiki/Downloads-of-old-versions) of all available releases


#### options.webkit_src
Type: `String`
Default value: `false`

This is where the prebuilt binaries and the releases are saved.

#### options.force
Type: `Boolean`
Default value: `false`

This will delete everything in your `webkit_src` directory, including the cached downloaded prebuilt binaries

#### options.win
Type: `Boolean`
Default value: `true`

Do you want to download and build a windows version

#### options.mac
Type: `Boolean`
Default value: `true`

Do you want to download and build a mac version

#### options.linux32
Type: `Boolean`
Default value: `true`

Do you want to download and build a linux32 version

#### options.linux64
Type: `Boolean`
Default value: `true`

Do you want to download and build a linux64 version


#### options.download_url
Type: `String`
Default value: `https://s3.amazonaws.com/node-webkit/`

The URL where the prebuilt binaries are. Only change this if you know what you are doing


### Usage Examples


```js
grunt.initConfig({
  nodewebkit: {
    options: {
        webkit_src: './webkitbuilds', // Where the build version of my node-webkit app is saved
        mac: true, // We want to build it for mac
        win: true, // We want to build it for win
        linux32: false, // We don't need linux32
        linux64: false // We don't need linux64
    },
    src: ['./example/public/**/*'] // Your node-wekit app
  },
})
```

## To Do:
- Test building on Windows and Linux machines

## Known Issue
This is the first relase so there might be bugs. One known issue is that the download sometimes fails. If this is the case just try to run the task again


## Release History
- 2013-08-13   initial release