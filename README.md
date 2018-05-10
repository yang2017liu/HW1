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

Process
After midterm, I changed the idea that using capacitive sensor and using gloves to express it. I want to use arduino to combine processing to make the sound become more elegant, but it is hard for me to figure out after I try so many times with coach. I try use the frequency to make the sound as much elegant as possible.


