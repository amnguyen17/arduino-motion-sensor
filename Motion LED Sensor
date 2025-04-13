/*
 * motion Activated Light System
 * arduino sketch turns on an LED when motion is detected
 * and turns it off when motion stops
 */

// pin Definitions
#define MOTION_SENSOR_PIN 2  // arduino pin connected to the OUTPUT pin of motion sensor
#define LED_PIN 30            // arduino pin connected to the LED

// Variables for motion detection
int motion_state = LOW;      // current state of motion sensor pin
int prev_motion_state = LOW; // previous state of motion sensor pin

void setup() {
  Serial.begin(9600);        // initialize Serial communication
  pinMode(MOTION_SENSOR_PIN, INPUT);  // set motion sensor pin as input
  pinMode(LED_PIN, OUTPUT);  // set LED pin as output
  
  Serial.println("Motion Activated Light System Initialized");
}

void loop() {
  // store the previous motion state
  prev_motion_state = motion_state;
  
  // read the current motion state
  motion_state = digitalRead(MOTION_SENSOR_PIN);
  
  // check if motion has started (pin state change: LOW -> HIGH)
  if (prev_motion_state == LOW && motion_state == HIGH) {
    Serial.println("Motion detected!");
    digitalWrite(LED_PIN, HIGH);  // turn on the LED
  } 
  // check if motion has stopped (pin state change: HIGH -> LOW)
  else if (prev_motion_state == HIGH && motion_state == LOW) {
    Serial.println("Motion stopped!");
    digitalWrite(LED_PIN, LOW);   // turn off the LED
  }
  
  // Small delay to stabilize readings
  delay(100);
}
