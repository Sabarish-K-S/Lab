1. Embedded Program Using Arduino To Control The Stepper Motor

```cpp
int IN1 = 8;
int IN2 = 9;
int IN3 = 10;
int IN4 = 11;
void setup(){
    pinMode(IN1, OUTPUT);
    pinMode(IN2, OUTPUT);
    pinMode(IN3, OUTPUT);
    pinMode(IN4, OUTPUT);
}
void loop() {
    digitalWrite(IN1, HIGH);
    digitalWrite(IN2, LOW);
    digitalWrite(IN3, LOW);
    digitalWrite(IN4, LOW);
    delay(10);
    digitalWrite(IN1, LOW);
    digitalWrite(IN2, HIGH);
    digitalWrite(IN3, LOW);
    digitalWrite(IN4, LOW);
    delay(10);
    digitalWrite(IN1, LOW);
    digitalWrite(IN2, LOW);
    digitalWrite(IN3, HIGH);
    digitalWrite(IN4, LOW);
    delay(10);
    digitalWrite(IN1, LOW);
    digitalWrite(IN2, LOW);
    digitalWrite(IN3, LOW);
    digitalWrite(IN4, HIGH);
    delay(10);
}
```
2. Embedded Program Using Arduino For Timer Control Operation

```cpp
void setup(){
    pinMode(LED_BUILTIN, OUTPUT);
}
void loop(){
    digitalWrite(LED_BUILTIN, HIGH);
    delay(2000);
    digitalWrite(LED_BUILTIN, LOW);
    delay(2000);
}
```    
3. Embedded Program Using Arduino For Control The Lighting System

```cpp
#define potPin A0
#define ledPin 9
void setup() {
    pinMode(ledPin, OUTPUT);
}
void loop() {
    int potValue = analogRead(potPin);
    int ledBrightness = map(potValue, 0, 1023, 0, 255);
    analogWrite(ledPin, ledBrightness);
}
```
4. Embedded Program Using Arduino For Controlling The Temperature

```cpp
int tempPin = A0;
float voltage = 0.0;
float temperatureC = 0.0;
void setup()
{
    pinMode(A0, INPUT);
    Serial.begin(9600);
}
void loop()
{
    int analogValue = analogRead(tempPin);
    voltage = (512 * 1.5) / 1023.0;
    temperatureC = voltage * 100.0;
    Serial.print("Temperature: ");
    Serial.print(temperatureC, 2);
    Serial.println(" degC");
    delay(1000);
}
```
5. Embedded Program Using Arduino For Display a Message In LCD

```cpp
#include <Adafruit_LiquidCrystal.h>
int seconds = 0;
Adafruit_LiquidCrystal lcd_1(0);
void setup()
{
    lcd_1.begin(16, 2);
    lcd_1.print("hello world");
}
void loop()
{
    lcd_1.setCursor(0, 1);
    lcd_1.print(seconds);
    lcd_1.setBacklight(1);
    delay(500);
    lcd_1.setBacklight(0);
    delay(500);
    seconds += 1;
}
```
