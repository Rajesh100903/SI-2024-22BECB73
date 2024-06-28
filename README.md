# SI-2024-22BECB73
📡 Repository for Summer Internship 2024"Intro to cubesat and satellite communication"
## Lab Exercises

## Lab-1 Introduction to ESP 32
-[Datasheet ESP 32](https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf)
## Lab-2 Blinking LED
-[Source File](Lab/arduino )
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


