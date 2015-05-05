# DLog is Log for Android

it works for only DEBUG mode

**when you develop**
- Log.xx() will show in your logcat view

**when you publish to googleplay**
- log.xx() will not show nowhere

##How to use

- make Base Application class in your project
```java
public class BaseApplication extends Application {
...
public static boolean DEBUG = false;
...


@Override
	public void onCreate() {
		super.onCreate();
    this.DEBUG = isDebuggable(this);
}

...
	/**
	 * get Debug Mode
	 * 
	 * @param context
	 * @return
	 */
	private boolean isDebuggable(Context context) {
		boolean debuggable = false;

		PackageManager pm = context.getPackageManager();
		try {
			ApplicationInfo appinfo = pm.getApplicationInfo(context.getPackageName(), 0);
			debuggable = (0 != (appinfo.flags & ApplicationInfo.FLAG_DEBUGGABLE));
		} catch (NameNotFoundException e) {
			/* debuggable variable will remain false */
		}

		return debuggable;
	}
	
}
```

- Use it anywhere like this:

AA.java

```java
public void test(){

Dlog.d("this is log");

}
```


- in logcat, you can see like this log

'[AA][test]this is log'

`Google Material Design Icons`
