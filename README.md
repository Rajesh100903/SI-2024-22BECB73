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

## Lab-5 Computing Signal Processing using Python through WSL
In signal processing, FFT forms the basis of frequency domain analysis (spectral analysis) and is used for signal filtering, spectral estimation, data compression, and other applications. Variations of the FFT such as the short-time Fourier transform also allow for simultaneous analysis in time and frequency domains. 
-In this module we would be using python to simulate signal processing.Python is a widely used interpreted language used in industries for data management, signal processing, application devolopment.
-[FFT using python](https://github.com/Rajesh100903/SI-2024-22BECB73/tree/main/Lab/arduino%20)


Frequency-shift keying (FSK) is a frequency modulation scheme in which digital information is encoded on a carrier signal by periodically shifting the frequency of the carrier between several discrete frequencies.
-[FSK ](https://github.com/Rajesh100903/SI-2024-22BECB73/blob/main/FFT1)


#### TO generate a cosine wave and plot the axis labelling[Cosine wave](https://github.com/Rajesh100903/SI-2024-22BECB73/blob/main/cos%20wave%20gen)

## Lab 6 Antenna design and configuration using 4NEC2 
4nec2 is a popular free NEC-2 based antenna modeler and optimizer for Windows. It allows users to design, analyze, and optimize antenna structures and calculate their properties such as radiation patterns, impedance, and more. Here's a brief overview and some guidance on how to use 4nec2.We can manufacture dipole antennas, horn shapped antennas , V shapped antennas.
-an example illustrating a loaded dipole in a free space-
 ``` 
CM Example 2 :	Loaded dipole in free space
CM 		See GetStarted.txt
CE 					' End of comment
'
SY len=.330				' Symbol: Length for WL/2
'
GW 1 9 0 -len/2 0 0 len/2 0 .0001	' Wire 1, 9 segments, halve wavelength long.
GE 0					' End of geometry
'
LD 5 1 0 0 5.8001E7			' Wire conductivity
'
EX 0 1 5 0 1 0				' Voltage source (1+j0) at wire 1 segment 5.
FR 0 1 0 0 433 0			' Set design frequency (300 Mc).
EN					' End of NEC input


- an example to set up V dipole
```
CM Example 2 :	Loaded dipole in free space
```
CM 		See GetStarted.txt
CE 					' End of comment
'
SY ylen=.1392				' Symbol: Length for WL/2
SY zlen=.0975
SY ysma=0.00409
SY zsma=0.00286			        ' Symbol: Length for WL/2
'
GW 1 9 0 -ylen zlen 0 -ysma zsma .0001	' Wire 1, 9 segments, halve wavelength long.
GW 2 9 0  ysma zsma 0  ylen zlen .0001	' Wire 2, 9 segments, halve wavelength long.
GW 3 1 0 -ysma zsma 0  ysma zsma .0001	' Wire 3, 9 segments, halve wavelength long.
GE 0					' End of geometry
'
LD 5 1 0 0 5.8001E7			' Wire conductivity
LD 5 2 0 0 5.8001E7			' Wire conductivity
LD 5 3 0 0 5.8001E7			' Wire conductivity
```
We had simulated various parameters such as impedance, SWR and the radiation pattern-

![Wse2](https://github.com/Rajesh100903/SI-2024-22BECB73/assets/173932157/feea9575-52a2-4107-a88d-13e9f503f980)
![Wse](https://github.com/Rajesh100903/SI-2024-22BECB73/assets/173932157/c000c0a1-a46f-435d-a2c5-e9d20cb2f96e)
![Wse3](https://github.com/Rajesh100903/SI-2024-22BECB73/assets/173932157/e7a183bc-0f2d-4303-ac83-1a84d9e7780b)

### -We can use a tiny VNA to simulate and tune our antennas and measure various parameters.
We had simulated VNA to calculate the SWR to be 1.147 impedance(Z) to be 51.09 ohm 52.9 pF and minimun frequency at 439 MHz.
![WhatsApp Image 2024-07-06 at 1 30 51 AM](https://github.com/Rajesh100903/SI-2024-22BECB73/assets/173932157/c22dcedb-8a55-4f0d-8ee5-64bc4761b7db)

