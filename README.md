int light = 2;  
int fan   = 3;  
int tv    = 4;  
char command;   
void setup() {
  pinMode(light, OUTPUT);
  pinMode(fan, OUTPUT);
  pinMode(tv, OUTPUT);
  Serial.begin(9600);
  Serial.println("welcome to home automation system");
  Serial.println("Send commands:");
  Serial.println("'1' = Light ON, '2' = Light OFF");
  Serial.println("'3' = Fan ON,   '4' = Fan OFF");
  Serial.println("'5' = TV ON,    '6' = TV OFF");
}
void loop() {
  if (Serial.available()) {
    command = Serial.read(); 
    switch (command) {
      case '1':
        digitalWrite(light, HIGH);
        Serial.println("Light ON");
        break;
      case '2':
        digitalWrite(light, LOW);
        Serial.println("Light OFF");
        break;
      case '3':
        digitalWrite(fan, HIGH);
        Serial.println("Fan ON");
        break;
      case '4':
        digitalWrite(fan, LOW);
        Serial.println("Fan OFF");
        break;
      case '5':
        digitalWrite(tv, HIGH);
        Serial.println("TV ON");
        break;
      case '6':
        digitalWrite(tv, LOW);
        Serial.println("TV OFF");
        break;
      default:
        Serial.println("Invalid Command! Use 1–6");
        break;
    }
  }
}
