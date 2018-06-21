CoocaaOSWebViewSDK面向Web前端开发提供的能力
=

## 基本介绍

该**SDK**扩展了若干功能插件深度对接酷开系统，将酷开系统的能力提供给Web前端使用，它是基于酷开系统Web前端开发的核心支撑组件。

基于该SDK打开的Web页面，可以对接酷开系统的能力以满足相关业务需求。


## 能力说明

*下面介绍的是sdk全部能力说明，不同的分支版本会有差异，具体可参见不同分支下的README文档*


<table>
  <tr>
    <th width=30%, bgcolor=yellow >表一(获取判断)</th>
    <th width=70%, bgcolor=yellow>详细描述</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>获取版本信息</td>
    <td>包括酷开系统版本号，Android版本号</td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>获取设备信息</td>
    <td>包括屏幕尺寸大小，机芯，机型，soc，激活id，设备id，EMMC，品牌</td>
  <tr>
    <td bgcolor=rgb(0,10,0)>获取内存信息</td>
    <td>包括总内存大小，剩余内存大小</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>获取空间信息</td>
    <td>包括总空间大小，剩余空间大小</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>获取用户信息</td>
    <td>包括sky_id,update_image_times,open_id,visit_num,accessToken，external_avatar等</td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>获取网络基本信息</td>
    <td>包括dns，gateway，ip地址，mac地址，子网掩码</td>
  </tr>
  <tr>
    <td bgcolor=rgb(0,10,0)>获取定位信息</td>
    <td>如广东省，深圳市</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>获取网络连接状态</td>
    <td>无</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>获取网络连接类型</td>
    <td>WiFi或Ethernet</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>判断用户是否登录</td>
    <td>无</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>退出当前登录</td>
    <td>无</td>
  </tr>
   <tr>
    <td bgcolor=#eeeeee>获取应用信息</td>
    <td>根据包名获取应用版本信息，判断是否安装该应用，支持列表查询</td>
  </tr>
   <tr>
    <td bgcolor=#eeeeee>获取WebViewSDK版本</td>
    <td>获取当前集成的WebViewSDK的版本，不同的版本有不同的能力支持</td>
  </tr>
   <tr>
    <td bgcolor=#eeeeee>获取酷开系统主题色</td>
    <td>分深色和浅色两种</td>
  </tr>
    <tr>
    <td bgcolor=#eeeeee>获取系统属性</td>
    <td>根据属性的key值获取对应的value值</td>
  </tr>
</table>

<table>
  <tr>
    <th width=30%, bgcolor=yellow >表二(启动跳转)</th>
    <th width=70%, bgcolor=yellow>详细描述</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>启动Activity</td>
    <td>封装的通用启动Activity方法，支持包名启动，action启动，包名/类名启动，支持设置type，Uri参数，支持附加多键值对参数</td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>check应用信息</td>
    <td>类似于获取获取应用信息</td>
   </tr>
  <tr>
    <td bgcolor=rgb(0,10,0)>启动在线播放</td>
    <td>有两种方式启动播放，只支持全屏播放</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>启动下载任务</td>
    <td>包括总空间大小，剩余空间大小</td>
  </tr>
   <tr>
    <td bgcolor=#eeeeee>启动账户界面</td>
    <td>也是调用通用的Activity启动方法</td>
  </tr>
     <tr>
    <td bgcolor=#eeeeee>启动网络设置界面</td>
    <td>也是调用通用的Activity启动方法</td>
  </tr>
     <tr>
    <td bgcolor=#eeeeee>启动主页界面</td>
    <td>也是调用通用的Activity启动方法</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>启动应用圈界面</td>
    <td>也是调用通用的Activity启动方法</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>退出当前页面</td>
    <td>退出当前页面，kill掉当前显示Web的Activity</td>
  </tr>
     <tr>
    <td bgcolor=#eeeeee>    ...</td>
    <td>    ...</td>
  </tr>
</table>

<table>
  <tr>
    <th width=30%, bgcolor=yellow >表三(消息监听)</th>
    <th width=70%, bgcolor=yellow>详细描述</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>监听网络状态变化</td>
    <td>当网络断开或连接时发送状态数据给Web前端，但前提是Web前端需要添加监听</td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>监听外接设备插拔变化</td>
    <td>当外接设备如U盘插拔时发送状态数据给Web前端，但前提是Web前端需要添加监听</td>
   </tr>
  <tr>
    <td bgcolor=rgb(0,10,0)>监听语音消息</td>
    <td>这跟具体业务相关，将预先定义好的口令以字符串（语音模块处理成字符串）的形式给Web前端，但前提是Web前端需要添加监听</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>监听支付状态变化</td>
    <td>当支付状态发生变化时发送数据给Web前端，但前提是Web前端需要添加监听</td>
  </tr>
   <tr>
    <td bgcolor=#eeeeee>监听通用状态变化</td>
    <td>根据不同的业务需求，Android端和Web端提前协商数据格式，当事件发生时Android端发送特定格式数据到Web端</td>
  </tr>
     <tr>
    <td bgcolor=#eeeeee>监听下载任务状态变化</td>
    <td>可监听下载成功，失败，进度等状态变化，但前提是Web前端需要添加监听</td>
  </tr>
     <tr>
    <td bgcolor=#eeeeee>监听用户状态变化</td>
    <td>当用户登录或退出时发送状态数据给Web前端，但前提是Web前端需要添加监听</td>
  </tr>
</table>

<table>
  <tr>
    <th width=30%, bgcolor=yellow >表四(按键监听)</th>
    <th width=70%, bgcolor=yellow>详细描述</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>监听按返回键down事件</td>
    <td>在Web页面上按下遥控器返回键时，会通知到Web前端，前提是需要监听返回键down事件</td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>监听按返回键up事件</td>
    <td>在Web页面上按遥控器返回键抬起时，会通知到Web前端，前提是需要监听返回键up事件</td>
   </tr>
   <tr>
    <td bgcolor=#eeeeee>监听按主页键</td>
    <td>在Web页面上按遥控器主页键时，会通知到Web前端，需要设置监听</td>
  </tr>
     <tr>
    <td bgcolor=#eeeeee>监听按音量键加减</td>
    <td>在Web页面上按遥控器按音量键加减时，会通知到Web前端，需要设置监听</td>
  </tr>
     <tr>
    <td bgcolor=#eeeeee>启动按菜单键</td>
    <td>在Web页面上按菜单键时，会通知到Web前端，需要设置监听</td>
  </tr>
    <tr>
    <td bgcolor=rgb(0,10,0)>监听Resume事件</td>
    <td>监听Resume事件，同Android Activity的生命周期</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>监听Pause事件</td>
    <td>监听Pause事件，同Android Activity的生命周期</td>
  </tr>
</table>

<table>
  <tr>
    <th width=30%, bgcolor=yellow >表五(日志提交)</th>
    <th width=70%, bgcolor=yellow>详细描述</th>
  </tr>
  <tr>
    <td bgcolor=rgb(0,10,0)>提交自定义事件</td>
    <td>可根据业务需求，自定义日志事件，并提交至酷开系统大数据后台</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>提交页面曝光时长</td>
    <td>可根据业务需求，并提交页面的光爆时长至酷开系统大数据后台，该功能有两个接口，需要成对调用，并保证页面名称一致</td>
  </tr>
</table>

<table>
  <tr>
    <th width=30%, bgcolor=yellow >表六(自定义业务)</th>
    <th width=70%, bgcolor=yellow>详细描述</th>
  </tr>
  <tr>
    <td bgcolor=rgb(0,10,0)>设置业务数据</td>
    <td>建立Web前端与NativeApp的数据通道，满足设置数据的业务需求，分同步和异步两种方式</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>获取业务数据</td>
    <td>建立Web前端与NativeApp的数据通道，满足获取数据的业务需求，分同步和异步两种方式</td>
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
 
 
 1.视频播放的支持？
 2.设置ua？
