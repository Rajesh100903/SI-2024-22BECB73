# SI-2024-22BECB73
📡 Repository for Summer Internship 2024"Intro to cubesat and satellite communication"
## Lab Exercises😊
## Arduino 🗜
Arduino is an open-source hardware and software company, project, and user community that designs and manufactures single-board microcontrollers and microcontroller kits for building digital devices.We are using ESP 32 microcontroller which is cheap, easily available used to send data and recieve data in satellite communication with integrated wifi facility and dual bluetooth mode. 
## ESP 32 
ESP32 is a series of low-cost, low-power system on a chip microcontrollers with integrated Wi-Fi and dual-mode Bluetooth.
## Lab-1 Introduction to ESP 32
-We had been introduced to the ESP 32 board and its operations and pin configurations used to transmit data from the computer to ESP and hence it is named as a micro-processor. The image of ESP 32 board which we will be using is [ESP32 configuration](https://www.robotdazero.it/blog/esp32-i-segreti-del-suo-successo/)
- We had attached the datasheet specifictions indicting the parameters under which the ESP 32 works indicating the temperature and other stuffs.
   [Datasheet ESP 32](https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf)
## Lab-2 Blinking LED 
-Blinking LED lights are some of the most popular bulbs used today. The blinking light is simply a light that goes on and off in a specific pattern. The pattern can be fast or slow and the lights can be a solid color or a variety of different colors.
-Here we go to the code we can refer to for LED blinking-
### code for led dimming
```C
int LEDpin = 13;
int delayT = 1000;
void setup() {
// put your setup code here, to run once:
pinMode(LEDpin, OUTPUT);
}
void loop() {
// put your main code here, to run repeatedly:
digitalWrite(LEDpin, HIGH);
delay(delayT);
digitalWrite(LEDpin, LOW);
delay(delayT);
}
```
### Lab-3 Dimming LED
Parameters from LED datasheet
| Parameters | Value|
|----------|-------|
|max forward current | 30ma |
|typical for voltage | 1.85V |
|dominant wavelength| 640 nm|
|color of light | deep red|
|typical capacitance | 45pF|
|op temperature range | -40 to 85 C|


