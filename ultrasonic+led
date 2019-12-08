//This is a distance mapping tool, measured by ultrasonic sensor, displayed by led

int trigPin = 3;
int echoPin = 2;
int ledPinclose = 8;
int ledPinmid = 9;
int ledPinfar = 10;
long distance;
long duration;

void setup() {
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
pinMode(ledPinclose, OUTPUT);
pinMode(ledPinmid, OUTPUT);
pinMode(ledPinfar, OUTPUT);
Serial.begin(9600);
}

void loop() {
  ultra();
  led();
  Serial.println("distance = " + String(distance));
}

void ultra(){

digitalWrite(trigPin, LOW);
delayMicroseconds(2);


digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);


duration = pulseIn(echoPin, HIGH);


distance= duration*0.034/2;
}

void led(){
if(distance>15 && distance<25){
    digitalWrite(ledPinfar, HIGH);
    digitalWrite(ledPinmid, LOW);
    digitalWrite(ledPinclose, LOW);
}
else if(distance>5 && distance<15){
    digitalWrite(ledPinmid, HIGH);
    digitalWrite(ledPinfar, HIGH);
    digitalWrite(ledPinclose, LOW);
}
else if(distance<5){
    digitalWrite(ledPinclose, HIGH);
    digitalWrite(ledPinmid, HIGH);
    digitalWrite(ledPinfar, HIGH);
}
else{
    digitalWrite(ledPinfar, LOW);
    digitalWrite(ledPinmid, LOW);
    digitalWrite(ledPinclose, LOW);
}
}
