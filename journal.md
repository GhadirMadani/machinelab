# Homework — Due Tuesday, 10 February 2026

## Motor Exercise (In-Class)

### Description

For this assignment, I completed the motor exercise we started in class using an H-bridge and a DC motor. The goal was to control the direction and speed of the motor using Arduino.

I wired the motor to pins 7 and 8 for direction control, and pin 9 for speed control using PWM.

---

### Schematic



---

### Arduino Code

```cpp
int motor1pin1 = 7;
int motor1pin2 = 8;

void setup() {
  pinMode(motor1pin1, OUTPUT);
  pinMode(motor1pin2, OUTPUT);
  pinMode(9, OUTPUT); 
}

void loop() {

  // Controlling speed (0 = off and 255 = max speed)
  analogWrite(9, 100); // ENA pin

  // Rotate in one direction
  digitalWrite(motor1pin1, HIGH);
  digitalWrite(motor1pin2, LOW);
  delay(5000);

  // Change speed and direction
  analogWrite(9, 200); // ENA pin

  digitalWrite(motor1pin1, LOW);
  digitalWrite(motor1pin2, HIGH);
  delay(3000);
}
``` 

After completing the class exercise, I modified the timing and speed values to create a smoother back-and-forth rotation for a Minecraft head attached to the motor.
``` cpp
int motor1pin1 = 7;
int motor1pin2 = 8;

void setup() {
  pinMode(motor1pin1, OUTPUT);
  pinMode(motor1pin2, OUTPUT);
  pinMode(9, OUTPUT); 
}

void loop() {

  // Controlling speed (0 = off and 255 = max speed)     
  analogWrite(9, 50); // ENA pin

  digitalWrite(motor1pin1, HIGH);
  digitalWrite(motor1pin2, LOW);
  delay(700);

  analogWrite(9, 50); // ENA pin
  digitalWrite(motor1pin2, HIGH);
  digitalWrite(motor1pin1, LOW);
  delay(700);
}
```

