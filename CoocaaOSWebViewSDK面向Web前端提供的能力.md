CoocaaOSWebViewSDK Android App集成文档
=

## 基本介绍

该**SDK**扩展了若干功能插件深度对接酷开系统，将酷开系统的能力提供给Web前端使用，它是基于酷开系统Web前端开发的核心支撑组件。

基于该SDK打开的Web页面，可以对接酷开系统的能力以满足相关业务需求。


## 能力说明

*下面介绍的是sdk全部能力说明，不同的分支版本会有差异，具体可参见不同分支下的README文档*


<table>
  <tr>
    <th width=40%, bgcolor=yellow >功能</th>
    <th width=60%, bgcolor=yellow>详细描述</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>获取版本信息</td>
    <td>包括酷开系统版本号，Android版本号</td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>获取设备信息</td>
    <td>包括panel大小，机芯，机型，soc，MAC地址，激活id，设备id，EMMC，品牌</td>
  <tr>
    <td bgcolor=rgb(0,10,0)>获取内存信息</td>
    <td>包括总内存大小，剩余内存大小</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>获取空间信息</td>
    <td>包括总空间大小，剩余空间大小</td>
  </tr>
</table>

## 版本描述

> ``历史更新参见各分支README文档`` [链接地址](https://github.com/fanyanbo/CoocaaOSWebViewSDK) <br/>
```
1. master分支：稳定版本分支
2. release/v2.4.0分支：增加了View的集成方式，该分支不稳定，内测状态
3. release/v2.5.0分支：稳定版本分支，除了不支持View方式集成外，目前具备最完善的功能
4. release/jiangsu分支：稳定版本分支，供第三方（江苏）使用，裁剪部分使用不到的功能
```
 
 - **使用到的第三方库/版本/LICENSE说明**
 > 此SDK为酷开系统的一部分, 采用了Cordova框架，基于原始Cordova框架之上做了修改，原始Cordova框架遵循 Apache License Version 2.0 开放源代码授权协议。

- **联系方式**
 > 樊彦博  电子邮件：fanyanbo@skyworth.com
