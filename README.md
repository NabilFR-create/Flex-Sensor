# Flex-Sensor
This is the code developed for the flex sensor. The goal was to connect the flex sensor with a vibration motor as a part of a responsive smart backbrace system. 

TinkerCAD circuit design:
![image](https://github.com/user-attachments/assets/570b9aa7-287a-4c47-83cb-c4596275dfa8)


// C++ code
//
int sensor = 0;

void setup()
{
  pinMode(A0, INPUT);
  pinMode(8, OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  sensor = analogRead(A0);
  if (sensor < 20) {
    digitalWrite(8, HIGH);
  } else {
    digitalWrite(8, LOW);
  }
  
  Serial.print("sensor = ");
  Serial.println(sensor);
  delay(100); // Wait for 100 millisecond(s)
  
  if (sensor < 25){
    Serial.print("Correct posture");
    
    delay(100);
  }
}

