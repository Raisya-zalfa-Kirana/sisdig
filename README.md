const int relayPin = 8;
const int ldrPin = A0;

int lightThreshold = 500;

void setup() {
  Serial.begin(9600);
  pinMode(relayPin, OUTPUT);
  pinMode(ldrPin, INPUT);
}

void loop() {
  int ldrStatus = analogRead(ldrPin);
  if (ldrStatus <= lightThreshold) {
    digitalWrite(relayPin, HIGH);
    Serial.println("LDR is DARK, Relay is ON");
  }
  else {
    digitalWrite(relayPin, LOW);
    Serial.println("LDR is BRIGHT, Relay is OFF");
  }
  delay(100);
}
