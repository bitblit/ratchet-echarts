# node-echarts
Generate chart by [Apache ECharts](https://github.com/apache/incubator-echarts) in Nodejs.

This library is forked from [node-echarts](https://github.com/hellosean1025/node-echarts) to which it is highly
indebted.  I have forked it because that library appears to now be dormant, and I'd like to be able to use newer
versions of echarts, and the new prebuilt versions of canvas in my Lambda functions.  I also prefer typescript
and will be bringing in type information.

### Install

Note: Since this library depends on Echarts >= 5.x and node-canvas (canvas) >= 2.9.3, it auto-bundles in the 
correct native libraries (prebuilt) for Windows, OSX, and Linux - see [the canvas github page](https://github.com/Automattic/node-canvas) 
for details.  Therefore, all you have to do is:

```
npm install @bitblit/ratchet-echarts
```

### Usage

```typescript

import { EChartRatchet } from '../echart-ratchet';
import { EChartsOption } from 'echarts';
import fs from 'fs';

const options: EChartsOption = {
    // Some big echarts thing... see Echarts docs for how to build this
    //title: {
    //    text: 'test',
    //},
    //...
};

const canvasConfig: EChartCanvasConfig  = {
    width: 1000
    height: 500
}

const myChart: Buffer = await EChartRatchet.renderChart(options, canvasConfig);
fs.writeFileSync('somefile.png', myChart);

// Also could have just written
// await EChartRatchet.renderChartToPngFile('somefile.png', options, canvasConfig);

```

### EChartCanvasConfig

|name|type|default|description|
|---|---|---|---|
|width|Number|500|Image width|
|height|Number|500|Image height|
