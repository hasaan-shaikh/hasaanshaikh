# STARTER GUIDE TO CREATIVE COMPUTING 

An easier way to understand the fundementals of creative computing.

I wanted to create a starter which will allow users to be able to understand the basic concepts of creative computer. I struggled to get my head around the fundementals of the brief so i felt creating a list of instruction will be able to help. 

Essential Terms 
---------------

Physical computing 
------------------

Physical computing is something like the Arduino Starter Kit as its interacting with the real world via a computer. An example of this would be Automatic doors in a hotel lobby or voice recognition on your smartphone. Physical computing is part of our daily lives which has potential for huge scalebility. 

Examples of artwork via Physical Computer - Daniel Rozin (Wooden Mirror
------------------------------------------------------------------------

![image](https://user-images.githubusercontent.com/94447759/144478454-afdd8a06-a317-4efe-b4bd-2f84e89b7f8d.png)

Wooden Mirror" is an interactive sculpture made up of non-reflective square wooden pixels. The piece reflects any object or person in front of it, moving fast enough to create live animation.
The wooden mirror is an example of physical computing in the art world and the possiblities for the future. 

Readme.file 
-----------

A readmefile is the first interaction users have. Its a text file that contains information regarding a certain software , project , game. Usually this is included with a software to detail instructions , help or information about updates.

OpenSource 
----------

Open source is a software which contains a licence where the copyright holder gives the rights to use , study , chang and distribute the software. Open source software can be developed as a collaboration.

Now we've got the basics of terminology , lets get hands on with the basic version of starter kit. 

Push Button LED Guide
---------------------

What you need : 

![image](https://user-images.githubusercontent.com/94447759/144480218-3d3dab45-8310-4cc5-85a9-f5e2afbe139f.png)


For this tutorial you will need:

- Arduino uno
- Breadboard
- LED x 1
- 220 Ohm & 10 KOhm resistor (One of each)
- Push button

Assemble the wires as set up below :

![image](https://user-images.githubusercontent.com/94447759/144480403-fc438051-75ba-47a5-aee2-e1330ef6608e.png)

This is the code :
------------------


Vim
const int  buttonPin1 = 2;    // first push button
const int ledPin1 = 13;       // LED
const int  buttonPin2 = 4;    // second push button
int lastPin1State,lastPin2State;

void setup() 
{
  pinMode(buttonPin1, INPUT);
  pinMode(ledPin1, OUTPUT);
  pinMode(buttonPin2,INPUT);
}


void loop() 
{
  // read the pushbutton input pin:
  int pin1State = digitalRead(buttonPin1);
  int pin2State = digitalRead(buttonPin2);
  if (pin1State == HIGH && lastPin1State == LOW && pin2State == LOW ) 
  {
    digitalWrite(ledPin1,HIGH);
  }

  if (pin2State == HIGH && lastPin2State == LOW && pin1State == LOW) 
  {
    digitalWrite(ledPin1,LOW);
  }
  lastPin1State = pin1State;
  lastPin2State = pin2State;
  delay(10);  
}
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
const int  buttonPin1 = 2;    // first push button
const int ledPin1 = 13;       // LED
const int  buttonPin2 = 4;    // second push button
int lastPin1State,lastPin2State;
 
void setup() 
{
  pinMode(buttonPin1, INPUT);
  pinMode(ledPin1, OUTPUT);
  pinMode(buttonPin2,INPUT);
}
 
 
void loop() 
{
  // read the pushbutton input pin:
  int pin1State = digitalRead(buttonPin1);
  int pin2State = digitalRead(buttonPin2);
  if (pin1State == HIGH && lastPin1State == LOW && pin2State == LOW ) 
  {
    digitalWrite(ledPin1,HIGH);
  }
 
  if (pin2State == HIGH && lastPin2State == LOW && pin1State == LOW) 
  {
    digitalWrite(ledPin1,LOW);
  }
  lastPin1State = pin1State;
  lastPin2State = pin2State;
  delay(10);  
}
You need to notice the order :

Vim
const int  buttonPin1 = 2; 
const int ledPin1 = 13; 
const int  buttonPin2 = 4; 
1
2
3
const int  buttonPin1 = 2; 
const int ledPin1 = 13; 
const int  buttonPin2 = 4; 
If you change the order of buttons, the code simply may not work as expected. That is exactly what we wanted to say at the beginning – as Arduino adds an abstraction of real C or C++ language, for slightly difficult logic, things have higher chance to fail to upgrade own self.







