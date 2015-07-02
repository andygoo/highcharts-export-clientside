# Highcharts客户端导出

Highcharts 客户端导出扩展。

你可能需要将你的 Highcharts 图表导出为 图片或者 PDF文件，默认情况下，Highcharts 提供了在线导出服务器（http://export.highcharts.com），只需要点击对应的导出按钮即可实现导出功能。不幸的是，你可能遇到下述情况：

* 你的应用无法联网；
* 你的图表包含机密数据，你不想通过不安全的通道传输；
* 在线导出不符合你公司的安全隐私策略；
* 你不想在本地搭建导出服务器；
* 都什么年代了，浏览器端完全可以实现这些功能.


另外，本插件还提供了官方导出模块支持及导出“cvs”功能。


## 安装

Dependencies are not shipped, so you'll have to do the following:

```(sh)
bower install
```

Boom, you're done. Check the ```example.html``` file and mess with it.

Or just get `highcharts-export-clientside.js`.

## Dependencies

This module depends on:
* [HighCharts](http://www.highcharts.com/) obviously, remember guys, it isn't free for commercial usages;
* its exporting module, that is bundle with it;
* for rasterized images (PNG, JPEG), a module called `canvas-tools` with is based<sup>1</sup> on [canvg](https://github.com/gabelerner/canvg) licenced under MIT Licence;
* [jsPDF](https://parall.ax/products/jspdf) (its GitHub page is [overthere](https://github.com/MrRio/jsPDF)) for PDF support, licenced under MIT Licence;
* Pseudo-official [export-csv](https://github.com/highslide-software/export-csv/tree/master) module for CSV and XLS support, under MIT Licence.

The only dependencies you must use are HighCharts and HighCharts exporting module. If you want PNG/JPEG, add `canvas-tools`. If you want PDF support, add both `canvas-tools` and `jsPDF`. If a dependency is missing for a file type, the option will not be available in the export menu.

<sup>1</sup> There are issues with canvg, title/subtitle appearing twice, this kind of things which `canvas-tools` fixes. So I'd suggest to go with this one.

## Remarks, Issues, Other stuff

* ~~Rasterized images have an aspect ratio issue. I probably made a boo-boo somewhere.~~ That's fixed.
* This probably won't work on Internet Explorer has it uses HTML5 download feature and opens a data-uri as a fallback. ~~But IE has limited data-uri support so who knows.~~ Nope, but there are some shim/sham/polyfills so that's possible to do.
* When exporting into PDF, `sourceWidth` and `sourceHeight` are expressed in millimeters.

## Changelog

### v1.0.1 – 2015-04-27

* handling of URL options in export-csv options (highslide-software/export-csv#40)

## Credits

Written with the help of the following resources:
* that  [Stack Overflow Q/A](http://stackoverflow.com/questions/25630811/export-highcharts-to-pdf-using-javascript-and-local-server-no-internet-connec) and this [snippet/project](https://github.com/leighquince/HighChartLocalExport/) by @leighquince;
* this [JSFiddle](http://jsfiddle.net/gh/get/jquery/1.7.2/highslide-software/highcharts.com/tree/master/samples/highcharts/exporting/offline-download/) from the official [HighCharts documentation](http://www.highcharts.com/docs/export-module/export-module-overview)
