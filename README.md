# arduino-project-1
implemented a simple bot on arduino 
//L293D
//Motor A
const int motorPin1  = 5;  // Pin 14 of L293
const int motorPin2  = 6;  // Pin 10 of L293
//Motor B
const int motorPin3  = 10; // Pin  7 of L293
const int motorPin4  = 9;  // Pin  2 of L293
char ch;
//This will run only one time.
void setup(){
 
    //Set pins as outputs
    pinMode(motorPin1, OUTPUT);
    pinMode(motorPin2, OUTPUT);
    pinMode(motorPin3, OUTPUT);
    pinMode(motorPin4, OUTPUT);
    

  Serial.begin(ch);
  
  
   
  
  
}

void loop() {
	directionControl();

  
	
}

// This function lets you control spinning direction of motors
void directionControl() {
	// Set motors to maximum speed
	// For PWM maximum possible values are 0 to 255
	
 while(Serial.available()==0){}
  ch=Serial.read();
  
	// Turn on motor A & B

    
  if(ch=='w'){
	digitalWrite(motorPin1, HIGH);
	digitalWrite(motorPin2, LOW);
	digitalWrite(motorPin3, LOW);
	digitalWrite( motorPin4, HIGH);
	
  }
	// Now change motor directions
  else if(ch=='s'){
	digitalWrite(motorPin1, LOW);
	digitalWrite(motorPin2, HIGH);
	digitalWrite(motorPin3, HIGH);
	digitalWrite( motorPin4,LOW );
  }

	// right
  else if(ch=='a'){
	digitalWrite(motorPin1, LOW);
	digitalWrite(motorPin2, LOW);
	digitalWrite(motorPin3, HIGH);
	digitalWrite( motorPin4, LOW);
  }
  else if(ch=='d'){
    digitalWrite(motorPin1, HIGH);
	digitalWrite(motorPin2, LOW);
	digitalWrite(motorPin3, LOW);
	digitalWrite( motorPin4, LOW);
  }
}
