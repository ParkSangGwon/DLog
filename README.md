# DLog is Log for Android

it works for only DEBUG mode

when you develop, Log.xx() will show in your logcat view
when you publish to googleplay, log.xx() will not show nowhere

##Usage
AA.java

public void test(){
Dlog.d("this is log");
}



in logcat, you can see like this log
[AA][test]this is log
