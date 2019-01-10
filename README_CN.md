- ###  [ `Return | 首页` ](https://github.com/PicoSupport/PicoSupport)
* [AndroidDemo | 安卓](https://github.com/PicoSupport/PicoSupport/blob/master/android.md)
* [UnityDemo | Unity3d](https://github.com/PicoSupport/PicoSupport/blob/master/unity.md)

## Unity_Demo_StartAction

## Unity_Versions：
- 2017.1.0f3 Or UP

## Explain 说明：

- Unity_Demo_在demo的场景中 点击 "Setting" 按钮跳转到 原生3D设置界面。
- 点击 "Bluetooth" 按钮跳转到 原生蓝牙设置界面。
- 点击 "WIFI" 按钮跳转到 原生Wifi设置界面。
- 点击 "Controller" 按钮跳转到 手柄管理界面。
<img src="/Other/Screenshot.png" width="300"/>

``` C#
//示例：设置跳转蓝牙
string action = "android.settings.BLUETOOTH_SETTINGS";

public void startAction(string action){
		
     AndroidJavaClass jcPlayer = new AndroidJavaClass ("com.unity3d.player.UnityPlayer");

     AndroidJavaObject joActivity = jcPlayer.GetStatic<AndroidJavaObject> ("currentActivity");
	
     AndroidJavaObject joIntent = new AndroidJavaObject ("android.content.Intent",action);
		
     joActivity.Call("startActivity", joIntent);  
	
}
```
``` 
//请在AndroidManifest.xml添加权限
<action android:name="pui.settings.action.SETTINGS" />
<action android:name="pui.settings.action.BRIGHTNESS_SETTINGS" />
<action android:name="pui.settings.action.SOUND_SETTINGS" />
<action android:name="pui.settings.action.WIFI_SETTINGS" />
<action android:name="pui.settings.action.BLUETOOTH_SETTINGS" />
<action android:name="pui.settings.action.ACCESSORY_SETTINGS" />
<action android:name="pui.settings.action.APPLICATION_SETTINGS" />
<action android:name="pui.settings.action.GENERAL_SETTINGS" />
<action android:name="pui.settings.action.ABOUT_SETTINGS" />
<action android:name="pui.settings.action.CONTROLLER_SETTINGS" />
```

## Use 使用：
- 场景位置： Assets -> Scene -> PicoNeoHandleSwitch
- 打包后在pico设备使用

## Announcements 注意事项：
- 请注意在AndroidManifest.xml添加权限

