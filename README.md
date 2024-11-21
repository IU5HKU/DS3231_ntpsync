# DS3231 SYNC'ing with NTP Server
ESP8266 utility to sync time to DS3231 using an NTP server of choice

Nothing more to say, self explanatory, connect your DS3231 clock module to your ESP8266 and flash this sketch after have changed 
the SSID and Password with yours, after launched the sketch connects to the ntp of your choice (change it in line 60) and sync 
the time in the clock module.

How to connect the two boards:


```javascript
DS3231  VCC GND SDA SCL
        |    |   |   |
ESP8266 3v3 GND  D2  D1
```

this thing can be done in a better way taking in account the time consumed in the various calls and precisely set the clock when the second occour, but for my pourpose this is enough....for the moment...
Actually you can't do much better than this, DS3231 doesn't have a register to set millisecs, the only thing datasheet report is the new time stars to be used just after the 'seconds' register is written, and there is no way to know how much delay there is. New data will be hold in shadow register that will be subsequently copied over the real one, in this way the counter is never interrupted.
You can achieve a subsecond precision with this module, enough for most applications, but you can't have a millisec precision unluckly...
The module have also the possibility to act as a sort of PPS source, there is the possibility to set INT/SQW to 1hz output, not bad at all if you need some syncing in your apps.
