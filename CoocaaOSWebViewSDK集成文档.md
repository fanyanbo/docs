
CoocaaOSWebViewSDK Android-App集成文档
=

## 基本介绍

该**SDK**基于**Apache Cordova WebApp开源框架**，使用的浏览器内核为Android原生内核【后续会考虑多内核切换模式】。

该**SDK**扩展了若干功能插件深度对接酷开系统，将酷开系统的能力提供给Web前端使用，它是基于酷开系统Web前端开发的核心支撑组件。

集成该SDK的Android App具备展示Web页面的能力。

## 版本描述



## 集成说明

*兼容Android4.2（android-17）及以上版本，建议在Android6.0（android-23）及以上版本进行开发调试*

集成该SDK时请注意以下说面:

```
1. 建议采用Android Studio IDE进行开发
2. 该SDK为aar，同时它依赖了多个酷开系统jar和aar，但目前没有打包到一个arr中，需要在工程libs下引用多个aar和jar
3. 需要自定义XXXApplication，继承SkyApplication，同时在AndroidManifest.xml文件中配置android:name=".XXXApplication"
4. AndroidManifest.xml配置权限:   
   `<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>`
   `<uses-permission android:name="android.permission.INTERNET" />`
5. 创建XXXActivity，集成CordovaExtActivity，在onCreate中调用loadUrl即可加载指定Web页面（建议在onSuperCmdInit中调用）
```

## 代码示例

跑测试

```bash
$ make test
```

跑覆盖率测试

```bash
$ make test-cov
```

## 贡献
