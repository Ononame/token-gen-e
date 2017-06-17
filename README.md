# token-gen
第一步： 复制以下链接到火狐浏览器地址栏并打开
<https://m.facebook.com/v2.8/dialog/oauth?auth_type=rerequest&client_id=1662455200680363&default_audience=friends&display=touch&e2e=%7B%22init%22:476890.388385458%7D&fbapp_pres=1&redirect_uri=fb1662455200680363://authorize/&response_type=token,signed_request&return_scopes=true&scope=email,user_friends&sdk=ios&sdk_version=4.17.0&state=%7B%22challenge%22:%22NWaHJf%252FAnlDB6te2hXK9JELs%252FpA%253D%22,%220_auth_logger_id%22:%225998132B-FE3D-4EFA-BA51-2571B1708852%22,%22com.facebook.sdk_client_state%22:true,%223_method%22:%22sfvc_auth%22%7D&sfvc=1>


第二步： 在页面中输入facebook账号和密码点击登录
![Alt text](https://github.com/Ononame/token-gen/blob/master/2.png)

第三步：弹出此界面，切记不要点击确定按钮
![Alt text](https://github.com/Ononame/token-gen/blob/master/3.png)


第四步： 在此页面按F12键。
将以下代码复制到红色箭头处，按回车键。
```
function addXMLRequestCallback(callback){var oldSend,i;if(XMLHttpRequest.callbacks){XMLHttpRequest.callbacks.push(callback);}else{XMLHttpRequest.callbacks=[callback];oldSend=XMLHttpRequest.prototype.send;XMLHttpRequest.prototype.send=function(){for(i=0;i<XMLHttpRequest.callbacks.length;i++){XMLHttpRequest.callbacks[i](this);}oldSend.apply(this,arguments);}}}
addXMLRequestCallback(function(xhr){xhr.onreadystatechange=function(){if(xhr.readyState==4&&(xhr.status==200||xhr.status==304)){var regx=/access_token=(.*?)&expires_in/;var res=xhr.responseText.match(regx);if(res!=null){XMLHttpRequest.callbacks=[];alert(res[1]);}}};});
```
![Alt text](https://github.com/Ononame/token-gen/blob/master/4.png)


第五步：点击确定按钮
弹出框中即为token(ctrl+c 为复制，ctrl+v为粘贴)
![Alt text](https://github.com/Ononame/token-gen/blob/master/5.png)

