# HW1
https://github.com/yang2017liu

# Week3
A piano gudiance ( people can play a song without know any konwledge about music.)
![image](/photo/IMG20180208130503.jpg)
The light blinking will guide people to touch different. After touching the pushsensor above the shape, the speaker will relaese different tone. Then next light blink to guide people to go next. people can play a song just follow the light.

# week 4

Essential elements
Arduino
Breadboard
LED (bulb)
push sensors
Speaker buzzer
Battery

Steps:
1) Get the LED to blink one by one 
2) Get the speaker buzzer plays different tone by toch the push sensor
2) Put everything together
8) Attach battery and a switch

# week 7
A piano gudiance ( people can play a song without know any konwledge about music.)
![image](/photo/IMG20180208130503.jpg)
The light blinking will guide people to touch different. After touching the pushsensor above the shape, the speaker will relaese different tone. Then next light blink to guide people to go next. people can play a song just follow the light.

I did not document my first prototype. my first prototype is that light blinks one by one. this is code:

int timer = 500;

void setup() {
  // use a for loop to initialize each pin as an output:
  for (int thisPin = 2; thisPin < 11; thisPin++) {
    pinMode(thisPin, OUTPUT);
  }
}

void loop() {
  // loop from the lowest pin to the highest:
  for (int thisPin = 2; thisPin < 11; thisPin++) {
    // turn the pin on:
    digitalWrite(2, HIGH);
    delay(timer);
    // turn the pin off:
    digitalWrite(2, LOW);
    delay(timer);
   
     //third

      // loop from the lowest pin to the highest:
  for (int thisPin = 3; thisPin < 11; thisPin++) 
    // turn the pin on:
    digitalWrite(3, HIGH);
    delay(timer);
    // turn the pin off:
    digitalWrite(3, LOW);
    delay(timer);



   //4

      // loop from the lowest pin to the highest:
  for (int thisPin = 4; thisPin < 11; thisPin++) 
    // turn the pin on:
    digitalWrite(4, HIGH);
    delay(timer);
    // turn the pin off:
    digitalWrite(4, LOW);
    delay(timer);
  


//5   // loop from the lowest pin to the highest:
  for (int thisPin = 5; thisPin < 11; thisPin++) 
    // turn the pin on:
    digitalWrite(5, HIGH);
    delay(timer);
    // turn the pin off:
    digitalWrite(5, LOW);
    delay(timer);

    //6
    // loop from the lowest pin to the highest:
  for (int thisPin = 6; thisPin < 11; thisPin++) 
    // turn the pin on:
    digitalWrite(6, HIGH);
    delay(timer);
    // turn the pin off:
    digitalWrite(6, LOW);
    delay(timer);


    //7
    // loop from the lowest pin to the highest:
  for (int thisPin = 7; thisPin < 11; thisPin++) 
    // turn the pin on:
    digitalWrite(7, HIGH);
    delay(timer);
    // turn the pin off:
    digitalWrite(7, LOW);
    delay(timer);

    //8
    // loop from the lowest pin to the highest:
  for (int thisPin = 8; thisPin < 11; thisPin++) 
    // turn the pin on:
    digitalWrite(8, HIGH);
    delay(timer);
    // turn the pin off:
    digitalWrite(8, LOW);
    delay(timer);

    //9
// loop from the lowest pin to the highest:
  for (int thisPin = 9; thisPin < 11; thisPin++) 
    // turn the pin on:
    digitalWrite(9, HIGH);
    delay(timer);
    // turn the pin off:
    digitalWrite(9, LOW);
    delay(timer);

    //10

    // loop from the lowest pin to the highest:
  for (int thisPin = 10; thisPin < 11; thisPin++) 
    // turn the pin on:
    digitalWrite(10, HIGH);
    delay(timer);
    // turn the pin off:
    digitalWrite(10, LOW);
    delay(timer);
    }
    
}
combine the two things work together.
![image](/photo/IMG20180301124415.jpg)

I put the tone and light together.
![image](/photo/IMG20180301150737.jpg)
video of my working project https://drive.google.com/drive/folders/1mUx35bqMp1dFGFVYQGuQNDQreV9_JPdq


# final work

### Therapy gloves

With capacitive sensors and Led Lights. The lights light up orderly to guide people move their hand to touch the finger with the light. When you touch the sensor on the gloves, you will activate the sound from the speaker. By following the light to move your finger. you can get a song.

### Process

After midterm, I changed the idea that using capacitive sensor and using gloves to express it. I want to use arduino to combine processing to make the sound become more elegant, but it is hard for me to figure out after I try so many times with coach. I try use the frequency to make the sound as much elegant as possible.

![image](/photo/IMG20180426141034.jpg) 
![image](/photo/IMG20180426141045.jpg)
![image](/photo/IMG20180426141316.jpg)
![image](/photo/IMG20180426141342.jpg)

### prototype test
Link : https://drive.google.com/drive/folders/1mUx35bqMp1dFGFVYQGuQNDQreV9_JPdq

### final outcome

![image](/photo/_X0A9650.JPG)
![image](/photo/_X0A9677.JPG)
![image](/photo/_X0A9683.JPG)
![image](/photo/_X0A9684.JPG)

### Video Demo
Link : https://drive.google.com/drive/folders/1KQGRy1gQgDJMBPM3WDYBHH_rpInPo0z3



### Code

#include <CapacitiveSensor.h>
int ledPin1  = 7;
int ledPin2  = 11;
int ledPin3 = 12;
int ledPin4 = 22;
int count = 0;


 
 

  

CapacitiveSensor   cs_4_8 = CapacitiveSensor(4, 8); // 1M resistor between pins 4 & 8, pin 8 is sensor pin, add a wire and or foil
CapacitiveSensor   cs_9_10 = CapacitiveSensor(9, 10); // 1M resistor between pins 9 & 10, pin 10 is sensor pin, add a wire and or foil
CapacitiveSensor   cs_2_3 = CapacitiveSensor(2, 3); // 1M resistor between pins 2 & 3, pin 10 is sensor pin, add a wire and or foil
CapacitiveSensor   cs_24_26 = CapacitiveSensor(24, 26); // 1M resistor between pins 2 & 3, pin 10 is sensor pin, add a wire and or foil
int noteRest = 500;

void setup()
{


  Serial.begin(9600);
  pinMode(ledPin1,OUTPUT);
  pinMode(ledPin2,OUTPUT);
  pinMode(ledPin3,OUTPUT);
  pinMode(ledPin4,OUTPUT);
  

 //WHY?
  cs_4_8.set_CS_AutocaL_Millis(0xFFFFFFFF);// turn off autocalibrate on channel 1 - just as an example
  cs_9_10.set_CS_AutocaL_Millis(0xFFFFFFFF);// turn off autocalibrate on channel 1 - just as an example
  cs_2_3.set_CS_AutocaL_Millis(0xFFFFFFFF);// turn off autocalibrate on channel 1 - just as an example
   cs_24_26.set_CS_AutocaL_Millis(0xFFFFFFFF);// turn off autocalibrate on channel 1 - just as an example
 //Turn all 3 LEDs on - WHY? 
    digitalWrite(ledPin1,HIGH);
    //digitalWrite(ledPin2,HIGH);
    //digitalWrite(ledPin3,HIGH);
}

void loop()
{
  // Why "long"? Why not int?
  long sensor1 =  cs_4_8.capacitiveSensor(50);
  long sensor2 =  cs_9_10.capacitiveSensor(50);
  long sensor3 =  cs_2_3.capacitiveSensor(50);
  long sensor4 =  cs_24_26.capacitiveSensor(50);
// FOR DEBUG
  //Serial.println(sensor1);  // print sensor output
  //Serial.println(sensor2);  // print sensor output
  //Serial.println(sensor3);  // print sensor output

  // This code only runs a simple sequence 1, 2, 3
  // LEDs light and stay on until the corresponding key is pushed
  // then the next LED in sequence lights and stays on until...
  //digitalWrite(ledPin1,HIGH);
//  wait for key touch #1
  if (sensor1 >= 1000){
    if (count == 0) {
    tone(6, 261);   //play tone  1000Hz
     digitalWrite(ledPin1,LOW);  //LED off
     delay(noteRest); //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin2,HIGH);  // turn on -next- LED
     count++;
    }
    if (count == 3) {
       tone(6, 261);  //play tone 900Hz
       digitalWrite(ledPin1,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin4,HIGH);  // turn on -next- LED
       count ++;
    }
     if (count == 7) {
       tone(6, 261);  //play tone 900Hz
       digitalWrite(ledPin1,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin4,HIGH);  // turn on -next- LED
       count ++;
    }
      if (count == 9) {
       tone(6, 261);  //play tone 900Hz
       digitalWrite(ledPin1,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin3,HIGH);  // turn on -next- LED
       count ++;
    }
         if (count == 11) {
       tone(6, 349);  //play tone 900Hz
       digitalWrite(ledPin1,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin2,HIGH);  // turn on -next- LED
       count ++;
    }
          if (count == 13) {
       tone(6, 261);  //play tone 900Hz
       digitalWrite(ledPin1,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin4,HIGH);  // turn on -next- LED
       count ++;
    }
              if (count == 15) {
       tone(6, 440);  //play tone 900Hz
       digitalWrite(ledPin1,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin3,HIGH);  // turn on -next- LED
       count ++;
    }


    
  }
  
 if (sensor2 >= 1000) {
  if (count == 1) {
    tone(6, 261); //play tone 500Hz
     digitalWrite(ledPin2,LOW); //LED off
     delay(noteRest);  //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin3,HIGH);  // turn on -next- LED
     count++;
  }
 if (count == 5) {  
    tone(6, 329);  //play tone 900Hz
     digitalWrite(ledPin2,LOW); //LED off
     delay(noteRest);  //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin3,HIGH);  // turn on -next- LED
     count++;
  }
 
    if (count == 12) {  
    tone(6, 261);  //play tone 900Hz
     digitalWrite(ledPin2,LOW); //LED off
     delay(noteRest);  //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin1,HIGH);  // turn on -next- LED
     count++;
  }
      if (count == 17) {
       tone(6, 329);  //play tone 900Hz
       digitalWrite(ledPin2,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin4,HIGH);  // turn on -next- LED
       count ++;
    }
    if (count == 20) {
       tone(6, 466);  //play tone 900Hz
       digitalWrite(ledPin2,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin4,HIGH);  // turn on -next- LED
       count ++;
    }
      if (count == 23) {
       tone(6, 391);  //play tone 900Hz
       digitalWrite(ledPin2,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin4,HIGH);  // turn on -next- LED
       count ++;
    }
     
 
 }

 if (sensor3 >= 1000) {
    if (count == 2) {  
    tone(6, 293);  //play tone 900Hz
     digitalWrite(ledPin3,LOW); //LED off
     delay(noteRest);  //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin1,HIGH);  // turn on -next- LED
     count++;
  }

if (count == 6) {  
    tone(6, 261);  //play tone 900Hz
     digitalWrite(ledPin3,LOW); //LED off
     delay(noteRest);  //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin1,HIGH);  // turn on -next- LED
     count++;
  }
if (count == 10) {  
    tone(6, 391);  //play tone 900Hz
     digitalWrite(ledPin3,LOW); //LED off
     delay(noteRest);  //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin1,HIGH);  // turn on -next- LED
     count++;
  }

          if (count == 16) {
       tone(6, 349);  //play tone 900Hz
       digitalWrite(ledPin3,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin2,HIGH);  // turn on -next- LED
       count ++;
    }
     if (count == 19) {
       tone(6, 466);  //play tone 900Hz
       digitalWrite(ledPin3,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin2,HIGH);  // turn on -next- LED
       count ++;
    }
    if (count == 22) {
       tone(6, 349);  //play tone 900Hz
       digitalWrite(ledPin3,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin2,HIGH);  // turn on -next- LED
       count ++;
    }

   
 }

  if (sensor4 >= 1000){
    if (count == 4) {  
    tone(6, 349);  //play tone 900Hz
     digitalWrite(ledPin4,LOW); //LED off
     delay(noteRest);  //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin2,HIGH);  // turn on -next- LED
     count++;
  }

 if (count == 8) {  
    tone(6, 293);  //play tone 900Hz
     digitalWrite(ledPin4,LOW); //LED off
     delay(noteRest);  //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin1,HIGH);  // turn on -next- LED
     count++;
  }
if (count == 14) {  
    tone(6, 523);  //play tone 900Hz
     digitalWrite(ledPin4,LOW); //LED off
     delay(noteRest);  //wait for note to play
     noTone(6);  // stop tone here
     digitalWrite(ledPin1,HIGH);  // turn on -next- LED
     count++;
  }

               if (count == 18) {
       tone(6, 293);  //play tone 900Hz
       digitalWrite(ledPin4,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin3,HIGH);  // turn on -next- LED
       count ++;
    }

              if (count == 21) {
       tone(6, 440);  //play tone 900Hz
       digitalWrite(ledPin4,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin3,HIGH);  // turn on -next- LED
       count ++;
    }
           if (count == 24) {
       tone(6, 349);  //play tone 900Hz
       digitalWrite(ledPin4,LOW); //LED off
       delay(noteRest);  //wait for note to play
       noTone(6);  // stop tone here
       digitalWrite(ledPin3,HIGH);  // turn on -next- LED
       count ++;
    }  
  }
//  else if (sensor1 >= 1000) {
//    tone(6, 900);  //play tone 900Hz
//     digitalWrite(ledPin1,LOW); //LED off
//     delay(noteRest);  //wait for note to play
//     noTone(6);  // stop tone here
//     digitalWrite(ledPin3,HIGH);  // turn on -next- LED
//  }
//
//  else if (sensor3 >= 1000) {
//    tone(6, 900);  //play tone 900Hz
//     digitalWrite(ledPin3,LOW); //LED off
//     delay(noteRest);  //wait for note to play
//     noTone(6);  // stop tone here
//     digitalWrite(ledPin1,HIGH);  // turn on -next- LED
//  }
//



  else {
    // stop tone here
    noTone(6);
  }

}

