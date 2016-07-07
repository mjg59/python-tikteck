Python control for Tikteck LED bulbs
====================================

A simple Python API for controlling LED bulbs from [Tikteck](http://www.tikteck.com).

Example use
-----------

This will connect and set the bulb to full red, no green and no blue at 50% intensity. 
```
import tikteck

bulb = tikteck.tikteck("00:21:4d:00:00:01", "Smart Light", "password")
bulb.connect()
bulb.set_state(0xff, 0x00, 0x00, 0x80)
```

Password can be obtained by enabling developer mode on your phone and running "adb logcat" after running the Tikteck app. The password will be printed in the form

```
E LedoBleSDK: login =skName=======[Smart Light]=======skPw==[password]
``` 

where the value between square brackets is the password. If skName is not "Smart Light", pass the appropriate value rather than "Smart Light".
