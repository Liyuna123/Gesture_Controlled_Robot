Gesture Controlled Robot
The robot is controlled by an Arduino hand gesture control that can be worn on the hand. The control works through bluetooth, and the robot can turn in all directions with its 4 wheels.


| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Liyuna C | Basis Independent Silicon Valley | N/A | Incoming 8th Grader

<!--- **Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**-->

![Headstone Image](logo.svg)
  
<!--# Final Milestone

<!---**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**-->
<!---youtube video below -->
<!---<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE--->

# Final Milestone

<!--<iframe width="560" height="315" src="https://www.youtube.com/embed/JsxYq6JUvng?si=LoC-VAoXQ2ImqSWc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>-->

## Description

For my third milestone, I had the two components work together. The first step was to make sure the bluetooth works, which I had done in the previous milestone. The rest was primarily in the code, which I have 2 sets of, one for the robot (refer to "Final Robot Code"), and one for the controller (refer to "Final Controller Code"). One of the most importants lines for the controller code are for the accelerometer. The code for the accelerometer sets conditions so that if the angle at which the accelerometer is at is greater than a certain value, it is considered going a certain direction depending on which axis. It then sends a short message to the robot through bluetooth. The code for the robot includes codes that set the speed and commands to set the direction. Based on the commands recieved from the HC-05, the robot would go in the direction given from the controller. The speed, on the other hand, is set and is not changed by the accelerometer. After uploading the code, I was able to use the serial monitor to see what data was being recieved.

## How it works

**MPU6050:**
For the hand controller, a key component is the MPU6050, which I have also referred to as the accelerometer. The MPU6050 is capable of measuring an object's acceleration, temperature, and angular velocity. In my project, its primary use is measure the angle at which it is being held at. This is extremely important because my robot is controlled by gestures. The accelerometer works by detecting the force that is being put on the object. My code allows this data to be converted to a single letter of the following: f (forward), b (backward), r (right), l(left), or s(stop). This information is then sent to the robot through the HC-05, and the robot interprets the letter and decides which direction to go.

## Challenges

### Accelerometer
I faced an issue with the accelerometer showing 127 on all three axes, which was inaccurate. This means the data was not being recieved by the Arduino, meaning wiring was wrong. I fixed this by first switching out the accelerometer, which didn't work. Therefore, I switched the wiring so that SD pin would connect to SC pin of Arduino, not SD. This fixed it.
### Code

**Flags:**
I firsted changed the code to not include flags, which can be set to 1 and 0. This was unnecessary, so I removed it. This didn't solve the problem, though, so I decided to debug it using the serial monitor. 

**Serial Monitor:**
By adding a line that says "Serial.println('xy')," I was able to see what data was going through and which caused the problem. I first did this for the controller. I set the serial communication rate to 9600 bps, and the commands printed in the serial monitor, showing data from the accelerometer was going through. Then, I observed the serial monitor in the code for the robot, and it appeared scrambled and unreadable. Therefore, I changed the BT rate, which allows commmuncation with the device, which is the HC-05 in my case. I changed it to 38400 because I learned that it is the baud rate of the HC-05. 

## Next Step
For the next milestone, I will be adding my modifications.


# Second Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/JsxYq6JUvng?si=LoC-VAoXQ2ImqSWc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Description

For my second milestone, I built the hand controller of the robot and tested each component individually. The hand controller includes and Arduino Nano, HC-05 bluetooth module, and an accelerometer. The first step was put the Arduino Nano, accelerometer, and HC-05 in place. Then, I attached the battery with male header pins. Finally, I attached everything with hard jump wires and male to male jumper wires. On the robot controller, only the TX and RX pin on the HC-05 should be connected to the 2 and 3 (RX and TX) pins on the Arduino Nano. The SCL pin on the accelerometer should be connected to the A4 pin, and the SDA pin should be connected to A5. The next steps were to connect the two bluetooth modules and upload the code. While doing this, I made sure that the EN pin is connected to the 3.3V on the Arduino. I was able to pair the modules by first plugging the Arduinos to my laptop, then plugging the HC-05 into the Arduino. Then, I proceeded to open the Serial Monitor in Arduino IDE and send commands to assign each module as either the slave or master. A few commands include AT, which checks that the HC-05 is responsive, AT+ROLE, which assigns the HC-05 a role, AT+CMODE, which allows the master to bind to either any or one specific HC-05, and AT+BIND, which is used to bind the master to the slave. Once they were paired, I unplugged the EN pin. For the code, I used 3 seperate sets, which were all written in C++. The first one was very simple and a test to see that the Arduino boards were responsive. It allowed the light on the board to blink on and off when requested (refer to "Blink Test" code). The second code was to pair the HC-05s (refer to "AT Mode Code". It was also simple with code that set the RX and TX pins to 2 and 3. Because it was simple, I could isolate the issue to the two bluetooth modules instead of my code. Finally, the last code was to test the car and have it drive back and forth (refer to "Robot Testing Code"

## How it works

**Motor Driver:**
One of the key components of this milestone is the motor driver. It works with having the motors connected to its pins, which are screwed in. For the motor driver, polarity decides which direction is forward and backword. It is also able to switch directions without re-wiring through the H-Bridge. The H-Bridge allows the motor driver to control the direction of the DC motors by, in a way, acting as a "bridge" between the power source, which is either the battery or laptop, to the motor. 

**HC-05s:**
The HC-05s work by, as said earlier, setting a master and slave module. Once they are bound together, the HC-05 promptly sends messages between the two modules. 

## Challenges

### Powering Controller and body
The first challenge I faced was when first powering on the controller and body. The first batteries I was using were 1.2 V batteries, which I used 4 of. This totalled to 4.8 V, which was enough to power my motor driver and Arduino Uno, but not the HC-05. I isolated the issue by using a multimeter to measure how much power was given to the HC-05 when the Arduino Uno was plugged in to  my laptop, which powered on the HC-05. The multimeter showed around 6.5 volts, which was much more than the 4.8 that I was given. I decided to switch the batteries to 1.5 V AA batteries which totalled to 6V. While this wasn't as much power as my computer, it was still enough to allow the HC-05 to power on. 

### Pairing HC-05s
The second challenge I faced was when pairing the two HC-05. This was my biggest challenge in the project so far, as it took me a while to figure out. The first issue I faced when sending AT commands. At first, it was unresponsive because the serial baud rate was less than it needed to be. I thought it was because the Arduino Uno prefered 5V, while the bluetooth module prefered 3.3V. I was going to use resistors, but I decided against it because it turned out to be unnecessary. I found out it was the baud rate that was the issue, and, after fixing that, I was able to send the AT commands. That was when I faced my second issue, which was the two modules not pairing together. The commands were correct, so I decided to redo my wiring to make sure it was correct. This fixed the issue. 

### Re-Soldering wires
The third challenge I faced was while working on pairing the two modules, the previously soldered wires connecting the Arduino Nano to the battery fell apart. I had to resolder this later in the project. 

### Uploading Code

**Processor:** 
The first issue with uploading was with the processor. I had set the processor on my laptop when uploading my code was the ATmega328P (Old Bootloader). After playing around with the settings, I found out that the processor for the Arduino Nano was suppposed to be set to ATmega328P. 

**RX and TX pins:**
The second issue I faced while uploading the code was that code is uploaded to the 0 and 1 pins on the Arduino, which is otherwise known as the pins set to be TX and RX. Therefore, while uploading the code, I faced an issue. To solve it, I used the SoftwareSerial library and set my RX and TX pins to 2 and 3. 

### DC Motors
**Only One Side working:** 
For a while, only one side was working. I used a multimeter and found that 0V were reaching the motors on that side. I fixed this by resoldering everything on that side.

**Inconsistency:**
I found that the inconsistency was because the motors had to be operated by the battery because of my connections.

## Next Step

For the next milestone, I will be adding my sending my code and having the robot and controller work together.

## Image

![Image2](IMG_2186.HEIC)
![Image2](IMG_2073.HEIC)



# First Milestone

<!--**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**-->
<!---youtube video below -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/_bARJUOrQyM?si=nMIZuDmcr8LgFZNh" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Description

For my first milestone, I built the base of the robot. It includes 4 DC motors, a drive motor, 4 AAA batteries, and an Arduino Uno. The first step was to secure the DC motors and add a wheel to them. Then, I soldered wires to them which connected to the motor driver. Finally, I attached the battery case to the motor driver and the Arduino Uno to the motor driver with male to female wires. One of the most important things I had to do in Milestone 1 was being careful with the wire connections. On the robot body, the VCC on the HC-05 should be connected to the 5V on the Arduino Uno, the two ground pins should be connected, the TX pin should be connected to the RX pin, and vice versa. The ENA, In1, IN2, IN3, IN4, and ENB pins on the motor driver should be connected to the D10, D9, D8, D7, D6, and D5 pins on the Arduino Uno. On the robot controller, only the TX and RX pin on the HC-05 should be connected to the RX and TX pins on the Arduino Nano. The SCL pin on the accelerometer should be connected to the A4 pin, and the SDA pin should be connected to A5.

## Challenges

### Attaching wheel to DC motors
The first challenge I faced was when attaching the wheel to the DC motors. One of them would not stay, so I solved the issue by adding electrical tape to secure it. 

### Soldering wires to motors
The second issue I faced was with soldering the wires to the motors. It was important to be careful when doing that because the soldering iron melted the plastic multiple times. 

### Soldering wires to motor driver
The final issue I faced was when soldering the wires to each other to connect to the motor driver. Because they were supposed to be screwed in, it was difficult to control the amount of solder on the wires as to be sure that they can still be screwed in. I had to remove solder multiple times.

## Next Step

For the next milestone, I will be creating the controller and testing to see that each component works individually.

## Image
![Image1](IMG_2189.HEIC)

<!--For your first milestone, describe what your project is and how you plan to build it. You can include:
- An explanation about the different components of your project and how they will all integrate together
- Technical progress you've made so far
- Challenges you're facing and solving in your future milestones
- What your plan is to complete your project-->

# Schematics 
Here is the digital version of the schematics of my controller.
![Controller schematic](Schematic2.png)

Here is the digital version of the schematics of my robot.
![Robot schematic](schematic1.png)
</div>
<!--Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser.-->

# Code
<!--Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. -->
## Milestone 2 code
### Blink Test 

This test was used to check that the Arduinos are working
```c++
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function repeats the light turning on and off until turned off
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);  // turn the LED on (HIGH is the voltage level)
  delay(1000);                      // wait for a second
  digitalWrite(LED_BUILTIN, LOW);   // turn the LED off by making the voltage LOW
  delay(1000);                      // wait for a second
}
```
### AT Mode Code 

This was the code used while in AT mode.
```c++
#include <SoftwareSerial.h> //built in library to customize RX and TX pins
SoftwareSerial BTserial(2, 3); // RX = 2, TX = 3

void setup() {
 Serial.begin(9600);       // Serial Monitor baud rate
 BTserial.begin(38400);    // HC-05 AT mode baud rate
 Serial.println("Ready to send AT commands");
}

void loop() {
 if (BTserial.available()) Serial.write(BTserial.read());
 if (Serial.available()) BTserial.write(Serial.read());
}

```
### Robot Testing Code

This is the code I used to test the robot motor driver and motors to make sure they work and are synced in the right direction.
```c++
// ----- Pin assignments -----
const int ENA = 10;   // left-side speed (PWM)
const int IN1 = 9;    // left-side direction
const int IN2 = 8;

const int ENB = 5;    // right-side speed (PWM)
const int IN3 = 7;    // right-side direction
const int IN4 = 6;

// ----- Setup runs once -----
void setup() {
  // Direction pins
  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);

  // Enable (speed) pins
  pinMode(ENA, OUTPUT);
  pinMode(ENB, OUTPUT);

 
}

void loop() {
   // ----- Move forward -----
  digitalWrite(IN1, HIGH);   // left wheel forward
  digitalWrite(IN2, LOW);
  digitalWrite(IN3, HIGH);   // right wheel forward
  digitalWrite(IN4, LOW);

  analogWrite(ENA, 255);     // full speed (0-255)
  analogWrite(ENB, 255);

  delay(2000);               // drive 2 s

  // ----- Stop -----
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, LOW);
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, LOW);

  analogWrite(ENA, 0);       // motors off
  analogWrite(ENB, 0);
 
}
```
## Milestone 3 code

### Accelerometer and Gyroscope Testing Code 

This is the code I used to test that the Accelerometer is able to read basic information given. 
Here is the code of my robot.
```c++
// Basic demo for accelerometer readings from Adafruit MPU6050

#include <Adafruit_MPU6050.h>
#include <Adafruit_Sensor.h>
#include <Wire.h>

Adafruit_MPU6050 mpu;

void setup(void) {
  Serial.begin(115200);
  while (!Serial)
    delay(10); // will pause Zero, Leonardo, etc until serial console opens

  Serial.println("Adafruit MPU6050 test!");

  // Try to initialize!
  if (!mpu.begin()) {
    Serial.println("Failed to find MPU6050 chip");
    while (1) {
      delay(10);
    }
  }
  Serial.println("MPU6050 Found!");

  mpu.setAccelerometerRange(MPU6050_RANGE_8_G);
  Serial.print("Accelerometer range set to: ");
  switch (mpu.getAccelerometerRange()) {
  case MPU6050_RANGE_2_G:
    Serial.println("+-2G");
    break;
  case MPU6050_RANGE_4_G:
    Serial.println("+-4G");
    break;
  case MPU6050_RANGE_8_G:
    Serial.println("+-8G");
    break;
  case MPU6050_RANGE_16_G:
    Serial.println("+-16G");
    break;
  }
  mpu.setGyroRange(MPU6050_RANGE_500_DEG);
  Serial.print("Gyro range set to: ");
  switch (mpu.getGyroRange()) {
  case MPU6050_RANGE_250_DEG:
    Serial.println("+- 250 deg/s");
    break;
  case MPU6050_RANGE_500_DEG:
    Serial.println("+- 500 deg/s");
    break;
  case MPU6050_RANGE_1000_DEG:
    Serial.println("+- 1000 deg/s");
    break;
  case MPU6050_RANGE_2000_DEG:
    Serial.println("+- 2000 deg/s");
    break;
  }

  mpu.setFilterBandwidth(MPU6050_BAND_21_HZ);
  Serial.print("Filter bandwidth set to: ");
  switch (mpu.getFilterBandwidth()) {
  case MPU6050_BAND_260_HZ:
    Serial.println("260 Hz");
    break;
  case MPU6050_BAND_184_HZ:
    Serial.println("184 Hz");
    break;
  case MPU6050_BAND_94_HZ:
    Serial.println("94 Hz");
    break;
  case MPU6050_BAND_44_HZ:
    Serial.println("44 Hz");
    break;
  case MPU6050_BAND_21_HZ:
    Serial.println("21 Hz");
    break;
  case MPU6050_BAND_10_HZ:
    Serial.println("10 Hz");
    break;
  case MPU6050_BAND_5_HZ:
    Serial.println("5 Hz");
    break;
  }

  Serial.println("");
  delay(100);
}

void loop() {

  /* Get new sensor events with the readings */
  sensors_event_t a, g, temp;
  mpu.getEvent(&a, &g, &temp);

  /* Print out the values */
  Serial.print("Acceleration X: ");
  Serial.print(a.acceleration.x);
  Serial.print(", Y: ");
  Serial.print(a.acceleration.y);
  Serial.print(", Z: ");
  Serial.print(a.acceleration.z);
  Serial.println(" m/s^2");

  Serial.print("Rotation X: ");
  Serial.print(g.gyro.x);
  Serial.print(", Y: ");
  Serial.print(g.gyro.y);
  Serial.print(", Z: ");
  Serial.print(g.gyro.z);
  Serial.println(" rad/s");

  Serial.print("Temperature: ");
  Serial.print(temp.temperature);
  Serial.println(" degC");

  Serial.println("");
  delay(500);
}
```

## Final Robot Code

This is my final milestone's code for the robot. 
```c++
#include <SoftwareSerial.h>
SoftwareSerial BT_Serial(2, 3); // RX, TX

#define enA 10//Enable1 L298 Pin enA 
#define in1 9 //Motor1  L298 Pin in1 
#define in2 8 //Motor1  L298 Pin in1 
#define in3 7 //Motor2  L298 Pin in1 
#define in4 6 //Motor2  L298 Pin in1 
#define enB 5 //Enable2 L298 Pin enB 

char bt_data; // variable to receive data from the serial port
int Speed = 150; //Write The Duty Cycle 0 to 255 Enable Pins for Motor Speed  

void setup() { // put your setup code here, to run once

Serial.begin(9600); // start serial communication at 9600bps
BT_Serial.begin(38400); 

pinMode(enA, OUTPUT); // declare as output for L298 Pin enA 
pinMode(in1, OUTPUT); // declare as output for L298 Pin in1 
pinMode(in2, OUTPUT); // declare as output for L298 Pin in2 
pinMode(in3, OUTPUT); // declare as output for L298 Pin in3   
pinMode(in4, OUTPUT); // declare as output for L298 Pin in4 
pinMode(enB, OUTPUT); // declare as output for L298 Pin enB 

delay(200);
}
void loop(){
if(BT_Serial.available() > 0){  //if some date is sent, reads it and saves in state     
bt_data = BT_Serial.read(); 
Serial.println(bt_data);          
}
  
if(bt_data == 'f'){
      forward();  
      Speed=180;// if the bt_data is 'f' the DC motor will go forward
      }  
else if(bt_data == 'b'){
      backward(); 
      Speed=180; // if the bt_data is 'b' the motor will go backward
      }  
else if(bt_data == 'l'){
      turnLeft(); 
      Speed=250; // if the bt_data is 'l' the motor will turn left
      }  
else if(bt_data == 'r'){
      turnRight();
      Speed=250; // if the bt_data is 'r' the motor will turn right
      } 
else if(bt_data == 's'){
      Stop();  // if the bt_data 's' the motor will Stop
      }   

analogWrite(enA, Speed); // Write The Duty Cycle 0 to 255 Enable Pin A for Motor1 Speed 
analogWrite(enB, Speed); // Write The Duty Cycle 0 to 255 Enable Pin B for Motor2 Speed 

delay(50);
}

void forward(){  //forward
digitalWrite(in1, HIGH); //Right Motor forward Pin 
digitalWrite(in2, LOW);  //Right Motor backward Pin 
digitalWrite(in3, LOW);  //Left Motor backward Pin 
digitalWrite(in4, HIGH); //Left Motor forward Pin 
}

void backward(){ //backward
digitalWrite(in1, LOW);  //Right Motor forward Pin 
digitalWrite(in2, HIGH); //Right Motor backward Pin 
digitalWrite(in3, HIGH); //Left Motor backward Pin 
digitalWrite(in4, LOW);  //Left Motor forward Pin 
}

void turnRight(){ //turnRight
digitalWrite(in1, LOW);  //Right Motor forward Pin 
digitalWrite(in2, HIGH); //Right Motor backward Pin  
digitalWrite(in3, LOW);  //Left Motor backward Pin 
digitalWrite(in4, HIGH); //Left Motor forward Pin 
}

void turnLeft(){ //turnLeft
digitalWrite(in1, HIGH); //Right Motor forward Pin 
digitalWrite(in2, LOW);  //Right Motor backward Pin 
digitalWrite(in3, HIGH); //Left Motor backward Pin 
digitalWrite(in4, LOW);  //Left Motor forward Pin 
}

void Stop(){ //stop
digitalWrite(in1, LOW); //Right Motor forward Pin 
digitalWrite(in2, LOW); //Right Motor backward Pin 
digitalWrite(in3, LOW); //Left Motor backward Pin 
digitalWrite(in4, LOW); //Left Motor forward Pin 
}

}


```
## Final Controller Code

This is the final code for my hand controller.
```c++
#include <SoftwareSerial.h>
SoftwareSerial BT_Serial(2, 3); // RX, TX

#include <Wire.h> // I2C communication library

const int MPU = 0x68; // I2C address of the MPU6050 accelerometer
int16_t AcX, AcY, AcZ;

int flag=0;

void setup () {// put your setup code here, to run once

Serial.begin(9600); // start serial communication at 9600bps
BT_Serial.begin(38400); 

// Initialize interface to the MPU6050
Wire.begin();
Wire.beginTransmission(MPU);
Wire.write(0x6B);
Wire.write(0);
Wire.endTransmission(true);

delay(500); 
}

void loop () {
Read_accelerometer(); // Read MPU6050 accelerometer

if(AcX<60 ){
      //flag=1;
      BT_Serial.write('f');
      Serial.println('f');
      }
if(AcX>130){
     // flag=1; 
      BT_Serial.write('b');
      Serial.println('b');}
      
if(AcY<60){
     // flag=1; 
      BT_Serial.write('l'); 
      Serial.println('l');
      }
if(AcY>130){
     // flag=1; 
      BT_Serial.write('r');
      Serial.println('r');
      }
  
if((AcX>70)&&(AcX<120)&&(AcY>70)&&(AcY<120)){
      flag=0;
BT_Serial.write('s');
Serial.println('s');
}

delay(100);  
}

void Read_accelerometer(){
      // Read the accelerometer data
Wire.beginTransmission(MPU);
Wire.write(0x3B); // Start with register 0x3B (ACCEL_XOUT_H)
Wire.endTransmission(false);
Wire.requestFrom(MPU, 6, true); // Read 6 registers total, each axis value is stored in 2 registers

AcX = Wire.read() << 8 | Wire.read(); // X-axis value
AcY = Wire.read() << 8 | Wire.read(); // Y-axis value
AcZ = Wire.read() << 8 | Wire.read(); // Z-axis value

AcX = map(AcX, -17000, 17000, 0, 180);
AcY = map(AcY, -17000, 17000, 0, 180);
AcZ = map(AcZ, -17000, 17000, 0, 180);

Serial.print(AcX);
Serial.print("\t");
Serial.print(AcY);
Serial.print("\t");
Serial.println(AcZ); 
}
```
# Bill of Materials
This is a list of the materials required for my intensive project.

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Arduino UNO | Used on Robot Body | $22 | <a href="https://www.newark.com/arduino/a000066/dev-board-atmega328-arduino-uno/dp/78T1601?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| Arduino Nano R3 | Used on controller | $20 | <a href="https://www.newark.com/arduino/a000005/dev-board-atmega328-arduino-nano/dp/13T9275?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| Inertial Measurement Unit (IMU) (6 deg of freedom) | Used on controller | $7 | <a href="https://www.amazon.com/dp/B008BOPN40/?tag=octopart00-20/"> Link </a> |
| SparkFun Dual H-Bridge motor drivers L298| Used on robot body | $6.2 | <a href="https://www.newark.com/stmicroelectronics/l298n/mtr-driver-40-to-150degc-multiwatt/dp/10WX1394?rpsku=rel1%3A32M1527"> Link </a> |
| Solderless Breadboard Half Size| Used as base for controller | $4.6 | <a href="https://www.newark.com/adafruit/64/bread-board-prototype-electronics/dp/53W6131?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| HC-05 Bluetooth Module| Used to pair controller with robot | $10.4 | <a href="https://www.amazon.com/HiLetgo-Wireless-Bluetooth-Transceiver-Arduino/dp/B071YJG8DR/"> Link </a> |
| Male/Male Jumper Wires| N/A | N/A | <a href="https://www.newark.com/adafruit/758/wire-gauge-28awg/dp/88W2570?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| Male/Female Jumper Wires | N/A | N/A | <a href="https://www.newark.com/adafruit/826/wire-gauge-28awg/dp/88W2802?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| DC Motor, 12 V | Used on robot body | No longer available | <a href="https://www.newark.com/multicomp/287-2520/dc-geared-motor-180-1-180rpm-12v/dp/52Y4441?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| Pimoroni Maker Essentials - Micro-motors & Grippy Wheels | Used as wheels on DC motors | $30.5 | <a href="https://shop.pimoroni.com/products/maker-essentials-micro-motors-grippy-wheels?variant=1418711662602/"> Link </a> |
| 9V Battery Clip | Used to attach battery to controller | $0.5 | <a href="https://www.newark.com/keystone/233/battery-strap-9v-wire-lead/dp/22C4351?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| 9V battery (generic)| Used to power controller | $6 | <a href="https://www.amazon.com/TENS-Cell-9v-Battery-Blue/dp/B00BC9JNRY/"> Link </a> |
| Battery Holder, 18650 x 2| Used to attach battery to robot| $8 | <a href="https://www.newark.com/keystone/1048/battery-holder-18650-li-ion-2cell/dp/56T2029?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |


# Starter Project Milestone

<!--**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**-->
<!---youtube video below -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/hjAuse6q-Nc?si=5vD7hXNev6jRxSgg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>



**Description:**
My starter project was a retro arcade game console, which was a way to practice soldering both pins and wires. The project includes several displays, buttons, and wires. The first step for the starter project was soldering each of the displays and buttons on to the board. The next step was to solder the wires that were connected to the battery case to the board. The last step was to assemble the case and screw everything in.

**Challenges:**
The first challenge I faced was soldering the pins. Because they were so close together, it was important to be careful to not solder other pins. The second challenge I faced was soldering the wires. This was was a problem for me because I found it was difficult to keep them in place. To solve this issue, I first tried bending them to stay in place, which did not work, so I ended up using eletrical tape to hold them in place. Another issue I faced when soldering the wires was burning some of them. I fixed this by stripping more of the wire and being sure not to hold the soldering iron to them to long. The last challenge I faced was screwing in the case. I used the wrong screws multiple times, which I fixed after trial and error and looking at other students' projects.

**Next Step:**
Using the things I learned in the starter project, I would start working on my intensive project.

<!--# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.-->
