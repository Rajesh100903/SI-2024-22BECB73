# SI-2024-22BECB73
Repository for Summer Internship 2024"Intro to cubesat and satellite communication"
#**Lab Exercises**

##**Lab-1 Introduction to ESP 32**

##**Lab-2 Blinking LED**

'''C 
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
'''
