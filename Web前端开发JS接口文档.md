## 集成说明

集成该SDK时请注意以下几点:

```
1. 如果开发的web页面需要对接酷开系统功能，则需集成酷开系统cordova前端框架，这样web才具备与酷开系统交互的能力
2. 在调用酷开系统功能接口的js文件中，需要引用相应的功能插件
3. 如需调用提交日志，获取设备信息等功能接口，在要提前引用cordova.require("coocaa-plugin-coocaaosapi.coocaaosapi");
这样可使用coocaaosapi对象调用相应功能

```

<table>
  <tr>
    <th width=30%, bgcolor=yellow >日志提交相关接口</th>
    <th width=35%, bgcolor=yellow>描述</th>
    <th width=35%, bgcolor=yellow>参数</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>notifyJSLogInfo(eventId,data,function(message){},function(error){})</td>
    <td>coocaaosapi插件调用，提交自定义事件</td>
    <td>coocaaosapi插件调用，提交自定义事件</td>
  </tr>
  <tr>
    <td bgcolor=#00FF00>notifyJSLogResumeInfo(pageName,data,function(message){},function(error){})</td>
    <td>coocaaosapi插件调用，提交页面曝光开始事件</td>
    <td>pageName:需要统计曝光时长的自定义页面名称，data：字符串类型，如"{'key1':'value1','key2':'value2',...}"</td>
   </tr>
  <tr>
    <td bgcolor=rgb(0,10,0)>notifyJSLogPauseInfo(pageName,function(message){},function(error){})</td>
    <td>coocaaosapi插件调用，提交页面曝光结束事件</td>
    <td>pageName:需要统计曝光时长的自定义页面名称。注意：这里开始事件和结束事件必须成对调用，否则统计不到曝光时长，并且pageName需要保持一致</td>
  </tr>
</table>
