Pointering
A Smarthome controlling Ring

!!! Work in Progress !!!
This is not a finished project; I'm still working on it and haven't tested anything so far.


The Pointering is a ring with which you can point at lights in your room and make gestures to turn them ON or OFF or even dim them. 
The ring uses an ESP32-C3FH4 as its processor and has an ICM-20948 IMU for determining the direction you're pointing and the gestures you're making. 
The ring also comes with an APA102-2020 for indicating different things, a built-in EEPROM for storing WiFi settings and other information, a battery charging/protection circuit, and a power latch circuit to make it as energy-efficient as possible. 
I'm planning to use a 50mAh 10mm x 12mm x 5mm battery.

<img src="https://github.com/JacTech/Pointering/assets/90476032/5cad6eaf-0042-433d-8b2b-80475bfdc6a0" width=50% height=50%>

*the PCB in this picture is a earlyer version with the same dimensions as V1.0




The Basestation features an ESP8266, which the ESP32 C3 connects to via ESP-NOW to send its data to the station. The station then sends it to an MQTT broker, a KNX bus, or anything you can program :) 
Other features of the Basestation include:
- NRF24l01, mainly for my smarthome, which has WiFi and RF (if the WiFi fails).
- Ring of 7 SK6805SIDE-S LEDs to display the charge status of the ring.
- VCNL4040M3OE Proximity sensor to turn on the LEDs when someone gets close.
- Temperature sensor.
- CH340 to program the ESP8266 and a switch to choose between programming the ESP8266 or the ESP32 C3.
- An Ampere sensor to detect shorts on the contact pins and measure the charging current. When a short gets detected, a MOSFET will cut the charging pins from the voltage.
  (This is mainly because I had problems with this kind of connector in the past, where the pins weren't all aligned correctly and shorted).


  <img src="https://github.com/JacTech/Pointering/assets/90476032/34abfa28-d0e4-4daf-9e21-173cf1aaa179" width=50% height=50%>
