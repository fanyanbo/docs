
CoocaaOSWebViewSDK Android-App集成文档
=

## 基本介绍

该**SDK**基于**Apache Cordova WebApp开源框架**，使用的浏览器内核为Android原生内核【后续会考虑多内核切换模式】。

该**SDK**扩展了若干功能插件深度对接酷开系统，将酷开系统的能力提供给Web前端使用，它是基于酷开系统Web前端开发的核心支撑组件。

集成该SDK的Android App具备展示Web页面的能力。

## 版本描述



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

## 贡献
