# LifeHelper   
* 用户登录注册
* 语音机器人聊天  
* 微信精选文章   
* 物流和电话号码归属地查询   
* 相册   
* 个性化二维码扫描生成  
* 定位与查看地图  
      
### 涉及到的技术点：   
Bmob后端云技术、RxVolley网络框架、Picasso多图异步加载、zxing二维码库、百度地图API、科大讯飞TTS语音引擎、自定义键盘及逻辑、 Tomcat文件下载和更新、 CircleImageView圆形头像、PhotoView图片缩放拖拽、实现时间轴效果、自定义短信提醒框     

### 从哪些方面下手   
* Package  
* Application   
* Activity  
* Drawable   
* Values     
* UtilTools  
* StaticClass   

### 工具类--封装Log  
* 1 static Level DEBUG  细粒度信息事件对调试应用程序非常有帮助
* 2 static Level INFO   粗粒度级别上突出强调应用程序的运行过程
* 3 static Level WARN   出现潜在错误
* 4 static Level ERROR  错误实际  
* 5 static Level FATAL  严重错误事件     

Log-->开关  log.i(tag,text)   
```   
package com.imooc.smartbutler.utils;
import android.util.Log;

public class L {
    //开关
    public static final  boolean DEBUG = true;
    //TAG
    public static final String TAG = "Smartbutler";
    //五个等级  DIWE
    public static void d(String text){
        if(DEBUG){
            Log.d(TAG,text);
        }
    }

    public static void i(String text){
        if(DEBUG){
            Log.i(TAG,text);
        }
    }

    public static void w(String text){
        if(DEBUG){
            Log.w(TAG,text);
        }
    }

    public static void e(String text){
        if(DEBUG){
            Log.e(TAG,text);
        }
    }
}
  ```
