Ultra Low Cost LoRa Gateway with ESP8266 modules

================================================



This project was based on the work of professor Congduc Pham's "Low Cost LoRa Gateway" project, available in https://github.com/CongducPham/LowCostLoRaGw



It uses low cost (US$2) ESP8266 and LoRa modules with the chip Semtech SX1272 or HOPERF's RFM95W modules (about US$8). The same modules are used for both sensor nodes and the gateway, but in the sensor nodes the WiFi support is disabled to lower the power consumption to less than 250 microamperes.

Arduino modules, like Pros (3.3V), can still be used on sensor nodes.

The original gateway project (based on RPI) was very simplified in this version to adapt to ESP8266 modules, with only Thingspeak support for while. In the example, the gateway transmits to Thingspeak site three fields, with RSSI, SNR and the ADC voltage each 10 minutes. After the transmition, the nodes enters in "deeepsleep" mode.  



The original SX1272 library was changed to include "yield()" statements in the receive process loop. This statement free the processor to do other tasks, avoiding crashes.



The connection to the HopeRF RFM95W LoRa Module is made using the standard SPI pins on ESP8266 (12(MISO),13(MOSI),14(SCK) and 15(CS)), but the CS pin can be changed in sx1272.h file.



The support for compiling the ESP8266 code on the Arduino IDE is documented in https://github.com/esp8266/Arduino
