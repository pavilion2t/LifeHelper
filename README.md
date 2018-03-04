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
  
  ### 工具类--封装SharedPreferences    
  * SharedPreferences  
  根据Context获取SharedPreferences对象，edit方法获取Editor对象，通过Editor对象存储键值对，提交数据。    
  * SQLite  
  * ContentProvider   
  * File      
  
  ```   
  public class ShareUtils {

    public static final String NAME = "config";

    //键 值
    public static void putString(Context mContext,String key,String value){
        SharedPreferences sp = mContext.getSharedPreferences(NAME,Context.MODE_PRIVATE);
        sp.edit().putString(key,value).commit();
    }

    //键 默认值
    public static String getString(Context mContext,String key,String defValue){
        SharedPreferences sp = mContext.getSharedPreferences(NAME,Context.MODE_PRIVATE);
        return sp.getString(key,defValue);
    }

    //键 值
    public static void putInt(Context mContext,String key,int value){
        SharedPreferences sp = mContext.getSharedPreferences(NAME,Context.MODE_PRIVATE);
        sp.edit().putInt(key,value).commit();
    }

    //键 默认值
    public static int getInt(Context mContext,String key,int defValue){
        SharedPreferences sp = mContext.getSharedPreferences(NAME,Context.MODE_PRIVATE);
        return sp.getInt(key,defValue);
    }

    //键 值
    public static void putBoolean(Context mContext,String key,boolean value){
        SharedPreferences sp = mContext.getSharedPreferences(NAME,Context.MODE_PRIVATE);
        sp.edit().putBoolean(key,value).commit();
    }

    //键 默认值
    public static boolean getBoolean(Context mContext,String key,boolean defValue){
        SharedPreferences sp = mContext.getSharedPreferences(NAME,Context.MODE_PRIVATE);
        return sp.getBoolean(key,defValue);
    }

    //刪除 单个
    public static void deleShare(Context mContext,String key){
        SharedPreferences sp = mContext.getSharedPreferences(NAME,Context.MODE_PRIVATE);
        sp.edit().remove(key).commit();
    }

    //刪除 全部
    public static void deleAll(Context mContext){
        SharedPreferences sp = mContext.getSharedPreferences(NAME,Context.MODE_PRIVATE);
        sp.edit().clear().commit();
    }

}   
  ```
