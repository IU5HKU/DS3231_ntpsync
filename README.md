# DS3231 SYNC'ing with NTP Server
ESP8266 utility to sync time from DS3231 and NTP server of choice

Nothing more to say, self explanatory, connect your DS3231 clock module to your ESP8266 and flash this sketch after have changed 
the SSID and Password with yours, after launched the sketch connects to the ntp of your choice (change it in line 60) and sync 
the time in the clock module.

How to connect the two boards:

DS3231  VCC GND SDA SCL
         |   |   |   |
ESP8266 5+  GND  D2  D1

this thing can be done in a better way taking in account the time consumed in the various calls and precisely set the clock qhen the second occour, but for my pourpose this is enough....for the moment...
