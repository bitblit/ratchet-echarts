# node-echarts
Generate chart by [Apache ECharts](https://github.com/apache/incubator-echarts) in Nodejs.

This library is forked from [node-echarts](https://github.com/hellosean1025/node-echarts) to which it is highly
indebted.  I have forked it because that library appears to now be dormant, and I'd like to be able to use newer
versions of echarts, and the new prebuilt versions of canvas in my Lambda functions.  I also prefer typescript
and will be bringing in type information.

### Install
OS | Command
----- | -----
OS X | `brew install pkg-config cairo pango libpng jpeg giflib`
Ubuntu | `sudo apt-get install libcairo2-dev libjpeg8-dev libpango1.0-dev libgif-dev build-essential g++`
Fedora | `sudo yum install cairo cairo-devel cairomm-devel libjpeg-turbo-devel pango pango-devel pangomm pangomm-devel giflib-devel`
Solaris | `pkgin install cairo pango pkg-config xproto renderproto kbproto xextproto`
Windows | [Instructions on our wiki](https://github.com/Automattic/node-canvas/wiki/Installation---Windows)

```
npm install node-echarts
```

### Usage
```javascript
var node_echarts = require('node-echarts');
var config = {
    width: 500, // Image width, type is number.
    height: 500, // Image height, type is number.
    option: {}, // Echarts configuration, type is Object.
    //If the path  is not set, return the Buffer of image.
    path:  '', // Path is filepath of the image which will be created.
    enableAutoDispose: true  //Enable auto-dispose echarts after the image is created.
}

node_echarts(config)

```

### Config

|name|type|default|description|
|---|---|---|---|
|width|Number|500|Image width|
|height|Number|500|Image height|
|option|Object|{}|Echarts Options|
|path|String|-|Path is filepath of the image which will be created. If the path is empty, return buffer.|
|enableAutoDispose|Boolean|true|Enable auto-dispose echarts after the image is created.|
