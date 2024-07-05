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
-Here we go to the code we can refer to for LED blinking.
### code for led dimming 💡
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
## Lab-3 Dimming LED 💡
Parameters from LED datasheet
| Parameters | Value|
|----------|-------|
|max forward current | 30ma |
|typical for voltage | 1.85V |
|dominant wavelength| 640 nm|
|color of light | deep red|
|typical capacitance | 45pF|
|op temperature range | -40 to 85 C|

From the ESP 32 Datasheet
| Parameters | Values |
|------------|--------|
| max output voltage | 4.34 V|
| max output current that GPIO can source from supply to load | .06mA |
 equivalent resistance calculation-
 for the circuit as shown [GPIO->R->LED diode->0](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.instructables.com%2FControl-LED-Using-Raspberry-Pi-GPIO%2F&psig=AOvVaw16IUiKdm7cGV6s_MdmkBs4&ust=1720290916425000&source=images&cd=vfe&opi=89978449&ved=0CBQQjRxqFwoTCJD5iJ3FkIcDFQAAAAAdAAAAABAJ)

=>4.34-30x10pow(-3)(R)-0.7=0
=>R=3.64/30x10pow(-3)=121.33 ohms
#### so the equivalent resistance which we had choosen for our convienience was= 100 ohms 
code for controlling the led intensity-
``` C
int led = 5;
int brightness = 0;
int fadeamount = 5;
void setup() {
  pinMode(led,OUTPUT);
}
void loop() {
  analogWrite(led,brightness);
  brightness=brightness+fadeamount;
  if(brightness<=0 || brightness>=255) {
    fadeamount=-fadeamount;
  }
  delay(30);
}
```
##### Code to assign an input port for 2-step dimmer control.
Full intensity, 0: 25-percent intensity.
 ``` C
 #define ledcSetup
#define ledcAttachPin
const int ledpin = 18;
const int freq = 5000;
const int resolution = 8;
void setup() {
  ledcAttachPin(ledpin,freq,resolution);
} 
void loop() {
  for(int dutyCycle = 255; dutyCycle <= 0; dutyCycle++ ){
    ledcWrite(ledpin, dutyCycle);
    delay(1000);
  }
  for(int dutyCycle = 255; dutyCycle >=0; dutyCycle--){
    ledcWrite(ledpin, dutyCycle);
    delay(1000);
  }
}
```
## Lab-4 OLED Display 
An organic light-emitting diode (OLED), also known as organic electroluminescent (organic EL) diode,[1][2] is a type of light-emitting diode (LED) in which the emissive electroluminescent layer is an organic compound film that emits light in response to an electric current. This organic layer is situated between two electrodes; typically, at least one of these electrodes is transparent. OLEDs are used to create digital displays in devices such as television screens, computer monitors, and portable systems such as smartphones and handheld game consoles. A major area of research is the development of white OLED devices for use in solid-state lighting applications.
Image of OLED display-[128x64-Blue-I2C-OLED-Display](https://github.com/Rajesh100903/SI-2024-22BECB73/assets/173932157/ce7ed38b-4412-4fc6-af0b-457a75b29931)

Code to display in OLED display -[OLED](https://github.com/Rajesh100903/SI-2024-22BECB73/blob/main/Lab/arduino%20/oled%20display)

Serial monitor to OLED Display-[OLED Display](https://github.com/Rajesh100903/SI-2024-22BECB73/blob/main/Lab/arduino%20/oled%20display)

Temperature and humidity using DHT22 sensor and display it on a OLED display-[Temp Humid](https://github.com/Rajesh100903/SI-2024-22BECB73/blob/main/Lab/arduino%20/temperature%20and%20humidity%20sensor)

