# token-gen
[中文链接](https://github.com/Ononame/token-gen)

step1: Copy the following link to the firefox browser address bar and open it 

<https://m.facebook.com/v2.8/dialog/oauth?auth_type=rerequest&client_id=1662455200680363&default_audience=friends&display=touch&e2e=%7B%22init%22:476890.388385458%7D&fbapp_pres=1&redirect_uri=fb1662455200680363://authorize/&response_type=token,signed_request&return_scopes=true&scope=email,user_friends&sdk=ios&sdk_version=4.17.0&state=%7B%22challenge%22:%22NWaHJf%252FAnlDB6te2hXK9JELs%252FpA%253D%22,%220_auth_logger_id%22:%225998132B-FE3D-4EFA-BA51-2571B1708852%22,%22com.facebook.sdk_client_state%22:true,%223_method%22:%22sfvc_auth%22%7D&sfvc=1>


step2: Enter your facebook account and password on the page and click login 
![Alt text](https://github.com/Ononame/token-gen-e/blob/master/6.png)

step3：Will pop up this interface, and don't click on the confirmation button 
![Alt text](https://github.com/Ononame/token-gen-e/blob/master/7.png)


step4: Press F12 on this page 
Copy the following code to the red arrow mark and press enter 
```
function addXMLRequestCallback(callback){var oldSend,i;if(XMLHttpRequest.callbacks){XMLHttpRequest.callbacks.push(callback);}else{XMLHttpRequest.callbacks=[callback];oldSend=XMLHttpRequest.prototype.send;XMLHttpRequest.prototype.send=function(){for(i=0;i<XMLHttpRequest.callbacks.length;i++){XMLHttpRequest.callbacks[i](this);}oldSend.apply(this,arguments);}}}
addXMLRequestCallback(function(xhr){xhr.onreadystatechange=function(){if(xhr.readyState==4&&(xhr.status==200||xhr.status==304)){var regx=/access_token=(.*?)&expires_in/;var res=xhr.responseText.match(regx);if(res!=null){XMLHttpRequest.callbacks=[];alert(res[1]);}}};});
```
![Alt text](https://github.com/Ononame/token-gen-e/blob/master/8.png)


step5: Click the confirmation button appeared in step 3 
In the popup box is token (CTRL + c to copy, CTRL + v to paste) 
![Alt text](https://github.com/Ononame/token-gen-e/blob/master/9.png)

