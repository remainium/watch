wiring
rtc, screen sck/scl - esp 32 c3 GPIO 9
rtc, screen sda     - esp 32 c3 GPIO 8

other than that for the physical wiring (the former was for the code)

battery to tp4056 input
grounds are shared
3.7v is directly connected to the c3 3.3v

a button directly cuts the power from the charging board, the device does not have a deep sleep mode.

it should be noted that the componets used were
3.7v lipo battery with preinstalled BMS
SH1106 1.4 inch OLED display
DS3231 RTC
a associated coin cell
a tactile button connected directly to the charger output positive terminal
the TP4056 charger
M3 bolts and nuts 


* it should be noted that the code is not made by me completely, this was my first time working with a screen and wifi and rtc so it was too complex for me to reliably create, after some experimenantion with the codes seperatly like displaying hello world, connecting my esp32 to the wifi , connecting to the time server and some failures, i decided that i couldent completely create the code myself.

however the case and cover, the wiring and fitting and the general selection of hardware aswell as the iterations and core of the poject was all done by me, along with a few parts of the code, the entirety of which i understand.



an explanation to the code

in my case the code will begin by starting the components

then it will check for a flag called firstboot

if it is infact powering on for the first time then it will connect to the wifi
and then go to a server called (pool.ntp.org) , sets to the current ist

then it inputs that into the RTC

updates the firstboot flag to false and saves it permanently and disables the wifi

when it boots agian it will read the false firstbott and skip the wifi part entirly

this was made in arduino ide.

it also converts the 24 hour clock into 12 hour after gathering the data from the rtc
calculates if its AM or PM 

and uses a text string to print the date

| Name of components        | Amount  |  price($) | sources |
|---------------------------|---------|-----------|---------|
| E-paper 2.1 inch display  | 1       | 19.8      | Amazon  |
| Tactile buttons           | 1(10)   | 1.05      | Amazon  |
|  RTC (DS3231)             | 1       | 3.13      | amazon  |
|  SD card reader           | 1       | 1.04      | Amazon  |
| SD card                   | 1       | 4.17      | Amazon  |
| on/off switch             | 1(10)   | 0.57      | Amazon  |
