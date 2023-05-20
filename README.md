# electrical_github
//https://www.tinkercad.com/things/aicqwHyALNE-frantic-vihelmo/editel
int ledArray[] = {9,8,7,6,5,4,3,2};
int count = 0;
int timer = 50;

void setup() {
  for (count = 0; count < 8; count++) {
    pinMode(ledArray[count], OUTPUT);
  }
}
void loop() {
  for (count = 0; count < 8; count++) {
    digitalWrite(ledArray[count], HIGH);
    delay(timer);
    digitalWrite(ledArray[count + 1], HIGH);
    delay(timer);
    digitalWrite(ledArray[count], LOW);
    delay(analogRead(0) / 8);
  }
  for (count = 8; count > 0; count--) {
    digitalWrite(ledArray[count], HIGH);
    delay(timer);
    digitalWrite(ledArray[count - 1], HIGH);
    delay(timer);
    digitalWrite(ledArray[count], LOW);
    delay(analogRead(0) / 8);
  }
}
