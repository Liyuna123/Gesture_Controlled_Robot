Gesture Controlled Robot
The robot is controlled by an Arduino hand gesture control that can be worn on the hand. The control works through bluetooth, and the robot can turn in all directions with its 4 wheels.


| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Liyuna C | Basis Independent Silicon Valley | ? | Incoming 8th Grader

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



<!--# Second Milestone

<!--**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**-->
<!---youtube video below -->
<!--<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone-->

# First Milestone

<!--**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**-->
<!---youtube video below -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/_bARJUOrQyM?si=nMIZuDmcr8LgFZNh" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

**Description:**
For my first milestone, I built the base of the robot. It includes 4 DC motors, a drive motor, 4 AAA batteries, and an Arduino Uno. The first step was to secure the DC motors and add a wheel to them. Then, I soldered wires to them which connected to the motor driver. Finally, I attached the battery case to the motor driver and the Arduino Uno to the motor driver with male to female wires.

**Challenges:**
The first challenge I faced was when attaching the wheel to the DC motors. One of them would not stay, so I solved the issue by adding electrical tape to secure it. The second issue I faced was with soldering the wires to the motors. It was important to be careful when doing that because the soldering iron melted the plastic multiple times.

**Next Step:**
For the next milestone, I will be creating the controller and testing to see that each component works individually.

<!--For your first milestone, describe what your project is and how you plan to build it. You can include:
- An explanation about the different components of your project and how they will all integrate together
- Technical progress you've made so far
- Challenges you're facing and solving in your future milestones
- What your plan is to complete your project-->

# Schematics 
Here is the digital version of the schematics of my controller.
<div style="position: relative; width: 100%; padding-top: calc(max(56.25%, 400px));">
  <iframe src="https://app.cirkitdesigner.com/project/8f149cdc-0c70-488b-bb97-79c7e6b5062e?view=interactive_preview" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none;"></iframe>
</div>
Here is the digital version of the schematics of my robot.
<div style="position: relative; width: 100%; padding-top: calc(max(56.25%, 400px));">
  <iframe src="https://app.cirkitdesigner.com/project/8eff8dc9-2f8a-4b31-87ab-973624e91911?view=interactive_preview" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none;"></iframe>
</div>
<!--Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser.-->

<!--# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
```-->

# Bill of Materials
This is a list of the materials required for my intensive project.

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Arduino UNO | What the item is used for | $Price | <a href="https://www.newark.com/arduino/a000066/dev-board-atmega328-arduino-uno/dp/78T1601?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| Arduino Nano R3 | What the item is used for | $Price | <a href="https://www.newark.com/arduino/a000005/dev-board-atmega328-arduino-nano/dp/13T9275?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| Inertial Measurement Unit (IMU) (6 deg of freedom) | What the item is used for | $Price | <a href="https://www.amazon.com/dp/B008BOPN40/?tag=octopart00-20/"> Link </a> |
| SparkFun Dual H-Bridge motor drivers L298| What the item is used for | $Price | <a href="https://www.newark.com/stmicroelectronics/l298n/mtr-driver-40-to-150degc-multiwatt/dp/10WX1394?rpsku=rel1%3A32M1527"> Link </a> |
| Solderless Breadboard Half Size| What the item is used for | $Price | <a href="https://www.newark.com/adafruit/64/bread-board-prototype-electronics/dp/53W6131?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| HC-05 Bluetooth Module| What the item is used for | $Price | <a href="https://www.amazon.com/HiLetgo-Wireless-Bluetooth-Transceiver-Arduino/dp/B071YJG8DR/"> Link </a> |
| Male/Male Jumper Wires| What the item is used for | $Price | <a href="https://www.newark.com/adafruit/758/wire-gauge-28awg/dp/88W2570?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| Male/Female Jumper Wires | What the item is used for | $Price | <a href="https://www.newark.com/adafruit/826/wire-gauge-28awg/dp/88W2802?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| DC Motor, 12 V | What the item is used for | $Price | <a href="(https://www.newark.com/multicomp/287-2520/dc-geared-motor-180-1-180rpm-12v/dp/52Y4441?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25)/"> Link </a> |
| Pimoroni Maker Essentials - Micro-motors & Grippy Wheels | What the item is used for | $Price | <a href="(https://shop.pimoroni.com/products/maker-essentials-micro-motors-grippy-wheels?variant=1418711662602)/"> Link </a> |
| Rocker Switch, SPST| What the item is used for | $Price | <a href="https://www.newark.com/mcm/is-ec-rs12513/switch-operation/dp/95Y1410?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| 9V Battery Clip | What the item is used for | $Price | <a href="https://www.newark.com/keystone/233/battery-strap-9v-wire-lead/dp/22C4351?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |
| 9V battery (generic)| What the item is used for | $Price | <a href="https://www.amazon.com/TENS-Cell-9v-Battery-Blue/dp/B00BC9JNRY/"> Link </a> |
| Battery Holder, 18650 x 2| What the item is used for | $Price | <a href="https://www.newark.com/keystone/1048/battery-holder-18650-li-ion-2cell/dp/56T2029?COM=ref_hackster&CMP=Hackster-NA-project-94b13d-Jun-25/"> Link </a> |


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
