# SI-2024-22BECB73
📡 Repository for Summer Internship 2024"Intro to cubesat and satellite communication"
## Lab Exercises
## Arduino 🗜
Arduino is an open-source hardware and software company, project, and user community that designs and manufactures single-board microcontrollers and microcontroller kits for building digital devices.We are using ESP 32 microcontroller which is cheap, easily available used to send data and recieve data in satellite communication with integrated wifi facility and dual bluetooth mode. 
## Lab-1 Introduction to ESP 32
-[Datasheet ESP 32](https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf)
## Lab-2 Blinking LED
-[Source File](https://github.com/Rajesh100903/SI-2024-22BECB73/blob/main/Lab/arduino%20/lab1)
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


