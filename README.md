# HUMAN-FOLLOWING-ADVANCED-ROBOT-CODE-HUMAN-OBSTACLES-FOLLOWING-ADVANCED-ROBOT-OPERATING-CODE
HUMAN FOLLOWING ADVANCED ROBOT CODE / HUMAN/OBSTACLES FOLLOWING ADVANCED ROBOT 🤖 OPERATING CODE.         #include&lt;NewPing.h> #include&lt;Servo.h> #include&lt;AFMotor.h> #define RIGHT A2 #define LEFT A3 #define TRIGGER_PIN A1 #define ECHO_PIN A0 #define MAX_DISTANCE 100     NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);   AF_DCMotor Motor1(1,MOTOR12_1KHZ); AF_DCMotor Motor2(2,MOTOR12_1KHZ); AF_DCMotor Motor3(3,MOTOR34_1KHZ); AF_DCMotor Motor4(4,MOTOR34_1KHZ);  Servo myservo;   int pos =0;  void setup() {   // put your setup code here, to run once:   Serial.begin(9600); myservo.attach(10); { for(pos = 90; pos &lt;= 180; pos += 1){   myservo.write(pos);   delay(15); } for(pos = 180; pos >= 0; pos-= 1) {   myservo.write(pos);   delay(15); }for(pos = 0; pos&lt;=90; pos += 1) {   myservo.write(pos);   delay(15); } } pinMode(RIGHT, INPUT); pinMode(LEFT, INPUT);  }  void loop() {   // put your main code here, to run repeatedly:    delay(50);  unsigned int distance = sonar.ping_cm(); Serial.print("distance"); Serial.println(distance);   int Right_Value = digitalRead(RIGHT); int Left_Value = digitalRead(LEFT);  Serial.print("RIGHT"); Serial.println(Right_Value); Serial.print("LEFT"); Serial.println(Left_Value);  if((Right_Value==1) &amp;&amp; (distance>=10 &amp;&amp; distance&lt;=30)&amp;&amp;(Left_Value==1)){   Motor1.setSpeed(145);   Motor1.run(FORWARD);   Motor2.setSpeed(145);   Motor2.run(FORWARD);   Motor3.setSpeed(145);   Motor3.run(FORWARD);   Motor4.setSpeed(145);   Motor4.run(FORWARD); }else if((Right_Value==0) &amp;&amp; (Left_Value==1)) {   Motor1.setSpeed(200);   Motor1.run(FORWARD);   Motor2.setSpeed(200);   Motor2.run(FORWARD);   Motor3.setSpeed(100);   Motor3.run(BACKWARD);   Motor4.setSpeed(100);   Motor4.run(BACKWARD); }else if((Right_Value==1)&amp;&amp;(Left_Value==0)) {   Motor1.setSpeed(100);   Motor1.run(BACKWARD);   Motor2.setSpeed(100);   Motor2.run(BACKWARD);   Motor3.setSpeed(200);   Motor3.run(FORWARD);   Motor4.setSpeed(200);   Motor4.run(FORWARD); }else if((Right_Value==1)&amp;&amp;(Left_Value==1)) {   Motor1.setSpeed(0);   Motor1.run(RELEASE);   Motor2.setSpeed(0);   Motor2.run(RELEASE);   Motor3.setSpeed(0);   Motor3.run(RELEASE);   Motor4.setSpeed(0);   Motor4.run(RELEASE); }else if(distance > 1 &amp;&amp; distance &lt; 10) {   Motor1.setSpeed(0);   Motor1.run(RELEASE);   Motor2.setSpeed(0);   Motor2.run(RELEASE);   Motor3.setSpeed(0);   Motor3.run(RELEASE);   Motor4.setSpeed(0);   Motor4.run(RELEASE);   }  }


//PROTTOY RATUL SARKER //
//ADVANCED HUMAN / OBSTACLES FOLLOWING ROBOT 🤖 CODE.//



// First of all install Motor Driver & Newping library then upload this code in ARDUINO UNO R3 board.
 





#include<NewPing.h>

#include<Servo.h>

#include<AFMotor.h>

#define RIGHT A2

#define LEFT A3

#define TRIGGER_PIN A1

#define ECHO_PIN A0

#define MAX_DISTANCE 100

  



NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);





AF_DCMotor Motor1(1,MOTOR12_1KHZ);

AF_DCMotor Motor2(2,MOTOR12_1KHZ);

AF_DCMotor Motor3(3,MOTOR34_1KHZ);

AF_DCMotor Motor4(4,MOTOR34_1KHZ);



Servo myservo;

 

int pos =0;



void setup() {

  // put your setup code here, to run once:

  Serial.begin(9600);

myservo.attach(10);

{

for(pos = 90; pos <= 180; pos += 1){

  myservo.write(pos);

  delay(15);

} for(pos = 180; pos >= 0; pos-= 1) {

  myservo.write(pos);

  delay(15);

}for(pos = 0; pos<=90; pos += 1) {

  myservo.write(pos);

  delay(15);

}

}

pinMode(RIGHT, INPUT);

pinMode(LEFT, INPUT);



}



void loop() {

  // put your main code here, to run repeatedly:



  delay(50);

 unsigned int distance = sonar.ping_cm();

Serial.print("distance");

Serial.println(distance);





int Right_Value = digitalRead(RIGHT);

int Left_Value = digitalRead(LEFT);



Serial.print("RIGHT");

Serial.println(Right_Value);

Serial.print("LEFT");

Serial.println(Left_Value);



if((Right_Value==1) && (distance>=10 && distance<=30)&&(Left_Value==1)){

  Motor1.setSpeed(120);

  Motor1.run(FORWARD);

  Motor2.setSpeed(120);

  Motor2.run(FORWARD);

  Motor3.setSpeed(120);

  Motor3.run(FORWARD);

  Motor4.setSpeed(120);

  Motor4.run(FORWARD);

}else if((Right_Value==0) && (Left_Value==1)) {

  Motor1.setSpeed(200);

  Motor1.run(FORWARD);

  Motor2.setSpeed(200);

  Motor2.run(FORWARD);

  Motor3.setSpeed(100);

  Motor3.run(BACKWARD);

  Motor4.setSpeed(100);

  Motor4.run(BACKWARD);

}else if((Right_Value==1)&&(Left_Value==0)) {

  Motor1.setSpeed(100);

  Motor1.run(BACKWARD);

  Motor2.setSpeed(100);

  Motor2.run(BACKWARD);

  Motor3.setSpeed(200);

  Motor3.run(FORWARD);

  Motor4.setSpeed(200);

  Motor4.run(FORWARD);

}else if((Right_Value==1)&&(Left_Value==1)) {

  Motor1.setSpeed(0);

  Motor1.run(RELEASE);

  Motor2.setSpeed(0);

  Motor2.run(RELEASE);

  Motor3.setSpeed(0);

  Motor3.run(RELEASE);

  Motor4.setSpeed(0);

  Motor4.run(RELEASE);

}else if(distance > 1 && distance < 10) {

  Motor1.setSpeed(0);

  Motor1.run(RELEASE);

  Motor2.setSpeed(0);

  Motor2.run(RELEASE);

  Motor3.setSpeed(0);

  Motor3.run(RELEASE);

  Motor4.setSpeed(0);

  Motor4.run(RELEASE);

  }

 }
