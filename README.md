//# 1st-car-code
//this first car code was made during the month of may. We were preparing to the category of future engineers in the WRO robotics competition 2023. However this car doesn't respect the rule 11.3 that impose having a steering system in the car this is why the code was modified in the 2nd-car-code.

//front ultasonic:
const int echo=10;
const int trig=6;
long duration;
long distance;

//RIGHT ULTRASONIC:
const int echo2=7;
const int trig2=8;
long duration2;
long distance2;

//LEFT ULTRASONIC:
const int echo3=9;
const int trig3=10;
long duration3;
long distance3;

//MOTOR:
int in1 = 2;//RIGHT AND FRONT
int in2 = 3;//RIGHT AND BACK
int in3 = 4;//LEFT AND FRONT
int in4 = 5;//LEFT AND BACK
int en1 = A0 ;
int en2 = A1;

void setup() {
  // PUT YOUR SETUP CODE HERE, TO RUN ONCE:
  //FRONT
  pinMode(trig,OUTPUT);
  pinMode(echo,INPUT);
  //RIGHT
  pinMode(trig2,OUTPUT);
  pinMode(echo2,INPUT);
  //LEFT
  pinMode(trig3,OUTPUT);
  pinMode(echo3,INPUT);

  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(in3, OUTPUT);
  pinMode(in4, OUTPUT);
  pinMode(en1, OUTPUT);
  pinMode(en2, OUTPUT);

  Serial.begin(9600);
}

void loop() {
  // PUT YOUR MAIN CODE HERE, TO RUN REPEATEDLY:
  analogWrite(en1,255);
  digitalWrite(in1,HIGH);
  digitalWrite(in2,LOW);
  analogWrite(en2,255);
  digitalWrite(in3,HIGH);
  digitalWrite(in4,LOW);
  digitalWrite(trig,LOW);

  digitalWrite(trig,LOW);
  delayMicroseconds(1000);
  digitalWrite(trig,HIGH);
  delayMicroseconds(1000);
  digitalWrite(trig,LOW);
  duration=pulseIn(echo,HIGH);
  distance= 0.034*duration/2;
  Serial.println(distance);

  digitalWrite(trig2,LOW);
  delayMicroseconds(1000);
  digitalWrite(trig2,HIGH);
  delayMicroseconds(1000);
  digitalWrite(trig2,LOW);
  duration2=pulseIn(echo2,HIGH);
  distance2= 0.034*duration2/2;
  Serial.println(distance2);

  digitalWrite(trig3,LOW);
  delayMicroseconds(1000);
  digitalWrite(trig3,HIGH);
  delayMicroseconds(1000);
  digitalWrite(trig3,LOW);
  duration3=pulseIn(echo3,HIGH);
  distance3= 0.034*duration3/2;
  Serial.println(distance3);
  if(distance<20 and distance2<12 and distance3<12 ){
    while(distance<20){
      analogWrite(en1,255);
      digitalWrite(in1,LOW);
      digitalWrite(in2,255);
      analogWrite(en2,255);
      digitalWrite(in3,HIGH);
      digitalWrite(in4,LOW);
      
      digitalWrite(trig,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig,LOW);
      duration=pulseIn(echo,HIGH);
      distance= 0.034*duration/2;
      Serial.println(distance);

      digitalWrite(trig2,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig2,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig2,LOW);
      duration2=pulseIn(echo2,HIGH);
      distance2= 0.034*duration2/2;
      Serial.println(distance2);

      digitalWrite(trig3,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig3,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig3,LOW);
      duration3=pulseIn(echo3,HIGH);
      distance3= 0.034*duration3/2;
      Serial.println(distance3);
    }
  }
  else if(distance<20 and distance2>12 and distance3<12){
    while(distance<20){
      analogWrite(en1,85);
      digitalWrite(in2,LOW);
      digitalWrite(in1,HIGH);
      analogWrite(en2,255);
      digitalWrite(in4,LOW);
      digitalWrite(in3,HIGH);  

      digitalWrite(trig,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig,LOW);
      duration=pulseIn(echo,HIGH);
      distance= 0.034*duration/2;
      Serial.println(distance);

      digitalWrite(trig2,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig2,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig2,LOW);
      duration2=pulseIn(echo2,HIGH);
      distance2= 0.034*duration2/2;
      Serial.println(distance2);

      digitalWrite(trig3,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig3,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig3,LOW);
      duration3=pulseIn(echo3,HIGH);
      distance3= 0.034*duration3/2;
      Serial.println(distance3);
    }
  }
  else if(distance<20 and distance2<12 and distance3>12){
    while(distance<20){
      analogWrite(en1,255);
      digitalWrite(in2,LOW);
      digitalWrite(in1,HIGH);
      analogWrite(en2,85);
      digitalWrite(in4,LOW);
      digitalWrite(in3,HIGH);   

      digitalWrite(trig,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig,LOW);
      duration=pulseIn(echo,HIGH);
      distance= 0.034*duration/2;
      Serial.println(distance);

      digitalWrite(trig2,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig2,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig2,LOW);
      duration2=pulseIn(echo2,HIGH);
      distance2= 0.034*duration2/2;
      Serial.println(distance2);

      digitalWrite(trig3,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig3,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig3,LOW);
      duration3=pulseIn(echo3,HIGH);
      distance3= 0.034*duration3/2;
      Serial.println(distance3);   
    }
  }
  else if(distance<20 and distance2>12 and distance3>12){
    while(distance2>distance3){
      analogWrite(en1,85);
      digitalWrite(in2,LOW);
      digitalWrite(in1,HIGH);
      analogWrite(en2,255);
      digitalWrite(in4,LOW);
      digitalWrite(in3,HIGH);  

      digitalWrite(trig,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig,LOW);
      duration=pulseIn(echo,HIGH);
      distance= 0.034*duration/2;
      Serial.println(distance);

      digitalWrite(trig2,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig2,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig2,LOW);
      duration2=pulseIn(echo2,HIGH);
      distance2= 0.034*duration2/2;
      Serial.println(distance2);

      digitalWrite(trig3,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig3,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig3,LOW);
      duration3=pulseIn(echo3,HIGH);
      distance3= 0.034*duration3/2;
      Serial.println(distance3);    
    }    
  }
  //Si il est dans la amrge il marche droit:
  else if(distance>20 and (distance2)<(((distance2+distance3+14)/2)+3) and distance2>(((distance2+distance3+14)/2)-3)){
    while(distance>20 and (distance2)<(((distance2+distance3+14)/2)+3) and distance2>(((distance2+distance3+14)/2)-3)){ 
      analogWrite(en1,255);
      digitalWrite(in1,HIGH);
      digitalWrite(in1,LOW);
      analogWrite(en2,255);
      digitalWrite(in3,HIGH);
      digitalWrite(in4,LOW);

      digitalWrite(trig,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig,LOW);
      duration=pulseIn(echo,HIGH);
      distance= 0.034*duration/2;
      Serial.println(distance);

      digitalWrite(trig2,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig2,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig2,LOW);
      duration2=pulseIn(echo2,HIGH);
      distance2= 0.034*duration2/2;
      Serial.println(distance2);

      digitalWrite(trig3,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig3,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig3,LOW);
      duration3=pulseIn(echo3,HIGH);
      distance3= 0.034*duration3/2;
      Serial.println(distance3);
    }
  }
  else if(distance>20 and distance2<(((distance2+distance3)/2)-3)){
    while(distance>20 and distance2<(((distance2+distance3)/2)-3)){
      analogWrite(en1,255);
      digitalWrite(in1,HIGH);
      digitalWrite(in2,LOW);
      analogWrite(en2,255);
      digitalWrite(in3,HIGH);
      digitalWrite(in4,LOW);

      digitalWrite(trig,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig,LOW);
      duration=pulseIn(echo,HIGH);
      distance= 0.034*duration/2;
      Serial.println(distance);

      digitalWrite(trig2,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig2,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig2,LOW);
      duration2=pulseIn(echo2,HIGH);
      distance2= 0.034*duration2/2;
      Serial.println(distance2);

      digitalWrite(trig3,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig3,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig3,LOW);
      duration3=pulseIn(echo3,HIGH);
      distance3= 0.034*duration3/2;
      Serial.println(distance3);
    }
  }
  else if(distance>20 and distance3<(((distance2+distance3)/2)-3)){
    while(distance>20 and distance3<(((distance2+distance3)/2)-3)){    
      analogWrite(en1,255);
      digitalWrite(in1,HIGH);
      digitalWrite(in2,LOW);
      analogWrite(en2,190);
      digitalWrite(in3,HIGH);
      digitalWrite(in4,LOW);

      digitalWrite(trig,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig,LOW);
      duration=pulseIn(echo,HIGH);
      distance= 0.034*duration/2;
      Serial.println(distance);

      digitalWrite(trig2,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig2,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig2,LOW);
      duration2=pulseIn(echo2,HIGH);
      distance2= 0.034*duration2/2;
      Serial.println(distance2);

      digitalWrite(trig3,LOW);
      delayMicroseconds(1000);
      digitalWrite(trig3,HIGH);
      delayMicroseconds(1000);
      digitalWrite(trig3,LOW);
      duration3=pulseIn(echo3,HIGH);
      distance3= 0.034*duration3/2;
      Serial.println(distance3);
    }
  }
}
