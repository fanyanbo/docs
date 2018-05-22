
CoocaaOSWebViewSDK Android-App集成文档
=

## 基本介绍

该**SDK**基于**Apache Cordova WebApp开源框架**，使用的浏览器内核为Android原生内核【后续会考虑多内核切换模式】。

该**SDK**扩展了若干功能插件深度对接酷开系统，将酷开系统的能力提供给Web前端使用，它是基于酷开系统Web前端开发的核心支撑组件。

集成该SDK的Android App具备展示Web页面的能力。

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


## 集成说明

*兼容Android4.2（android-17）及以上版本，建议在Android6.0（android-23）及以上版本进行开发调试*

集成该SDK时请注意以下几点:

```
1. 建议采用Android Studio IDE进行开发
2. 该SDK为aar，同时它依赖了多个酷开系统jar和aar，但目前没有打包到一个arr中，需要在工程libs下引用多个aar和jar
3. 自定义XXXApplication，继承自SkyApplication，在AndroidManifest.xml文件中配置android:name=".XXXApplication"
4. AndroidManifest.xml配置权限:   
   `<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>`
   `<uses-permission android:name="android.permission.INTERNET" />`
5. 创建XXXActivity，继承自CordovaExtActivity，onCreate中调用loadUrl加载Web页面（建议在onSuperCmdInit中调用）
```

## 代码示例

集成说明中的第3点：
```
//XXXApplication.java文件
public class XXXApplication extends SkyApplication{

    private static final String mTag = "WebViewSDK";

    @Override
    public void onCreate() {
        // TODO Auto-generated method stub
        super.onCreate();
        Log.i(mTag,"XXXApplication onCreate");
    }
}

//AndroidManifest.xml文件，仅修改android:name的名称即可
<application
        android:name=".XXXApplication"
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
	...
```

集成说明中的第5点：

```
//根据实际业务需求实现相应接口
public class XXXActivity extends CordovaExtActivity
        implements CordovaExtActivity.CordovaWebViewListener, 
		   CordovaExtActivity.CordovaWebPageListener, 
		   CordovaExtActivity.CordovaBusinessDataListener 
{

    private String mDefaultUrl = "http://beta.webapp.skysrt.com/fyb/webapp/index.html";

    @Override
    public void onCreate(Bundle savedInstanceState) {

        setCordovaWebViewListener(this);
        setCordovaBusinessDataListener(this);
        setCordovaWebPageListener(this);

        LOG.setLogLevel(LOG.VERBOSE);

        super.onCreate(savedInstanceState);
    }

    @Override
    public void onSuperCmdInit() {
        loadUrl(mDefaultUrl);
    }

    @Override
    public void onPageStarted(String url) {
    }

    @Override
    public void onPageFinished(String url) {
    }

    @Override
    public void onPageError(int errorCode, String description, String failingUrl) {
    }

    @Override
    public void notifyMessage(String data) {
    }

    @Override
    public void notifyLogInfo(String eventId, Map<String, String> map) {
    }

    @Override
    public void notifyPageResume(String pageName, Map<String, String> map) {
    }

    @Override
    public void notifyPagePause(String pageName) {
    }

    @Override
    public String getBusinessData(String data) {
        return null;
    }

    @Override
    public boolean setBusinessData(String data) {
        return false;
    }
}
```

## 接口说明

<table>
  <tr>
    <th width=40%, bgcolor=yellow > </th>
    <th width=60%, bgcolor=yellow>说明</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>loadUrl(String url)</td>
    <td>不带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮 </td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>loadUrl(String url, boolean isNeedBg)</td>
    <td>第二个参数决定是否带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮</td>
  <tr>
    <td bgcolor=rgb(0,10,0)>loadUrl(String url, FrameLayout errorPageBg)</td>
    <td>不带系统背景，第二个参数决定是否采用默认的错误页面背景，可自定义错误页面</td>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>loadUrl(String url, boolean isNeedBg, boolean isNeedBtn, FrameLayout errorPageBg)</td>
    <td>第二个参数决定是否带系统背景，第三个参数决定是否在错误页上显示“去连网”或“刷新试试”按钮，第四个参数决定是否采用默认的错误页面背景 </td>
  </tr>
</table>

<table>
  <tr>
    <th width=40%, bgcolor=yellow >CordovaWebViewListener</th>
    <th width=60%, bgcolor=yellow>说明</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>onPageStarted(String url)</td>
    <td>不带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮 </td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>onPageFinished(String url)</td>
    <td>第二个参数决定是否带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮</td>
  <tr>
    <td bgcolor=rgb(0,10,0)>onPageError(int errorCode, String desc, String failingUrl)</td>
    <td>不带系统背景，第二个参数决定是否采用默认的错误页面背景，可自定义错误页面</td>
  </tr>
</table>

<table>
  <tr>
    <th width=40%, bgcolor=yellow >CordovaWebViewListener</th>
    <th width=60%, bgcolor=yellow>说明</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>onPageStarted(String url)</td>
    <td>不带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮 </td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>onPageFinished(String url)</td>
    <td>第二个参数决定是否带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮</td>
  <tr>
    <td bgcolor=rgb(0,10,0)>onPageError(int errorCode, String desc, String failingUrl)</td>
    <td>不带系统背景，第二个参数决定是否采用默认的错误页面背景，可自定义错误页面</td>
  </tr>
</table>

<table>
  <tr>
    <th width=40%, bgcolor=yellow >CordovaWebPageListener</th>
    <th width=60%, bgcolor=yellow>说明</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>notifyMessage(String data)</td>
    <td>不带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮 </td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>notifyLogInfo(String eventId, Map<String,String> map)</td>
    <td>第二个参数决定是否带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮</td>
  </tr>
  <tr>
    <td bgcolor=rgb(0,10,0)>notifyPageResume(String pageName, Map<String,String> map)</td>
    <td>不带系统背景，第二个参数决定是否采用默认的错误页面背景，可自定义错误页面</td>
  </tr>
  <tr>
    <td bgcolor=rgb(0,10,0)>notifyPagePause(String pageName)</td>
    <td>不带系统背景，第二个参数决定是否采用默认的错误页面背景，可自定义错误页面</td>
  </tr>
</table>

<table>
  <tr>
    <th width=40%, bgcolor=yellow >CordovaBusinessDataListener</th>
    <th width=60%, bgcolor=yellow>说明</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>String getBusinessData(String data)</td>
    <td>不带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮 </td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>boolean setBusinessData(String data)</td>
    <td>第二个参数决定是否带系统背景，采用默认的错误页面背景，错误页上有“去连网”或“刷新试试”按钮</td>
  </tr>
</table>

## 工程配置

