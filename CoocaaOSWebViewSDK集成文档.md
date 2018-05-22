
CoocaaOSWebViewSDK Android-App集成文档
=

## 基本介绍

该**SDK**基于**Apache Cordova WebApp开源框架**，使用的浏览器内核为Android原生内核【后续会考虑多内核切换模式】。

该**SDK**扩展了若干功能插件深度对接酷开系统，将酷开系统的能力提供给Web前端使用，它是基于酷开系统Web前端开发的核心支撑组件。

集成该SDK的Android App具备展示Web页面的能力。

## 版本描述



## 集成说明

*兼容Android4.2及以上版本，建议在android-23及以上版本进行开发调试*

线上跑的是 [Node.js](https://nodejs.org) v4.4.0，[MongoDB](https://www.mongodb.org) 是 v3.0.5，[Redis](http://redis.io) 是 v3.0.3。

```
1. 安装 `Node.js[必须]` `MongoDB[必须]` `Redis[必须]`
2. 启动 MongoDB 和 Redis
3. `$ make install` 安装 Nodeclub 的依赖包
4. `cp config.default.js config.js` 请根据需要修改配置文件
5. `$ make test` 确保各项服务都正常
6. `$ node app.js`
7. visit `http://localhost:3000`
8. done!
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
