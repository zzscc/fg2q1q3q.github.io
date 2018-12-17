/*
* moaBridge v1.0.0
* =======================
* Author: bester
* Update Date: 2018-09-27
*/
moaBridge = window.moaBridge || {};
moaBridge = {
    //预览
    preview: function({url,fileName,uid,appid}){
        if(is_android()){
            window.jsBridge.preview(url,fileName,uid,appid);
        }
        if(is_iphone()){
            if(iosVersion < 8){  
                window.jsBridge.preview({'url':url,'fileName':fileName,'uid':uid,'appid':appid});
            }else{
                window.webkit.messageHandlers.preview.postMessage({'url':url,'fileName':fileName,'uid':uid,'appid':appid});
            }
        }
        if(is_iPad()){
            window.webkit.messageHandlers.preview.postMessage({'url':url,'fileName':fileName,'uid':uid,'appid':appid});
        }
    },
    //下载
    download: function({url,fileName,uid,appid}){
        if(is_android()){
            window.jsBridge.download(url,fileName,uid,appid);
        }
        if(is_iphone()){
            if(iosVersion < 8){  
                window.jsBridge.download({'url':url,'fileName':fileName,'uid':uid,'appid':appid});
            }else{
                window.webkit.messageHandlers.download.postMessage({'url':url,'fileName':fileName,'uid':uid,'appid':appid});
            }
        }
        if(is_iPad()){
            window.webkit.messageHandlers.download.postMessage({'url':url,'fileName':fileName,'uid':uid,'appid':appid});
        }
    },
    close: function(){
        if(is_android()){
            window.jsBridge.close();
        }
        if(is_iphone()){
            if(iosVersion < 8){  
                window.jsBridge.close();
            }else{
                window.webkit.messageHandlers.close.postMessage();
            }
        }
        if(is_iPad()){
            window.webkit.messageHandlers.close.postMessage();
        }
    }

}
var ua = navigator.userAgent.toLowerCase();
var iosVersion = (navigator.appVersion).match(/OS (\d+)_(\d+)_?(\d+)?/);
if(is_iphone()){
    iosVersion = parseInt(iosVersion[1], 10);
}
//判断环境
function is_android(){
    if(ua.match(/android/i)=="android"&&ua.match(/iemobile/i)!="iemobile"){
         return true;
    } else {
         return false;
    }
}
function is_iphone(){
    if(ua.match(/iphone/i)=="iphone"&&ua.match(/iemobile/i)!="iemobile"){
         return true;
    } else {
         return false;
    }
}
function is_iPad(){
    if(ua.match(/iPad/i)=="iPad"||ua.match(/ipad/i)=="ipad"){
         return true;
    } else {
         return false;
    }
}
