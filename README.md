# Remote File Webpack Plugin

## What it does

Webpack 4 plugin to download remote files and save them in Webpack compilation, so they can be served locally.

## Requirements

* Webpack 4
* Node >= 10.12

## Install

```
npm install remote-file-webpack-plugin --save-dev
```

## Usage

```js
const RemoteFilePlugin = require('remote-file-webpack-plugin');

module.exports = {
  plugins: [
    new RemoteFilePlugin([
      {
        url: 'https://fonts.googleapis.com/css?family=Open+Sans:300,400,600,700,800|Roboto:100,300,400,500,700,900',
        filepath: 'styles/fonts.css',
        cache: true
      },
    ])
  ]
}
```

## Options

You can pass in either an object, or an array of objects for downloading multiple files.

* **url** (`string`): URL of the remote file
* **filepath** (`string`): path, relative to your local `output.path`, where the file will be saved
* **cache** (`boolean`): wether or not to use cache so you don't have to download same file multiple times (`node_modules\.cache\remote-file-webpack-plugin`)
