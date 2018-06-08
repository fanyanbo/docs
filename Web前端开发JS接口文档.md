<table>
  <tr>
    <th width=60%, bgcolor=yellow >功能接口</th>
    <th width=40%, bgcolor=yellow>描述</th>
  </tr>
  <tr>
    <td bgcolor=#eeeeee>coocaaosapi.notifyJSLogInfo(eventId,ddata,function(message) { },function(error) { console.log(error);})</td>
    <td>aaaa</td>
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
