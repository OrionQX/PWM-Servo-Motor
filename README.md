# PWM-Servo-Motor
PWM (pulse width modulation) servo control

#include <Servo.h>

Servo myServo;

int potPin = A0;
int potValue;
int servoPos;

void setup() {
  myServo.attach(9); 
  Serial.begin(9600);
}

void loop() {
  potValue = analogRead(potPin);
  servoPos = map(potValue, 0, 1023, 0, 255);
  myServo.write(servoPos);
  delay(15);
}
