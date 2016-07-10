# ArduinoRTKRecorder
A Recorder for gathering GPS raw data to be played through RTK software to get more accurate GPS location information


Based around an Arduino Nano, a Ublox NEO 7M (or 6M) and a small TFT (160 x 128) screen which also includes an SD Card Reader - links to each on Banggood.com below.

Display - http://www.banggood.com/1_8-Inch-Serial-SPI-TFT-LCD-Display-Module-With-Power-IC-SD-Socket-p-909802.html

GPS - http://www.banggood.com/Ublox-NEO-7M-Flight-Controller-GPS-Module-Built-in-Data-Memory-p-973621.html

Arduino Nano - http://www.banggood.com/ATmega328P-Nano-V3-Controller-Board-Compatible-Arduino-p-940937.html


The GPS is connected to the Hardware Serial port.  The Display and SD Card reader are connected using I2C on pins 9,10,11,12, with CS on pins 8 and 13(?)  

Basic flow is to initialise the screen and SD Card.  Wait for the GPS to initialise, and confirm communication at 9600 BAUD.  

Then the GPS needs to be configured for RTK information.  Because I am using the more basic GPS modules that are not able to output the UBLOX Raw messages, I am using the information provided by OpenStreetMap at the link below.  This details how to enable some undocumented messages that the NEO-7M module is able to output that the RTK library can interpret instead of the RAW message (apparently).

http://wiki.openstreetmap.org/wiki/UbloxRAW

