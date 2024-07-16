# arduino-radar-system
Building a home-made radar system using an Ultrasound sensor and an Arduino UNO.

Introduction

With the help of a micro servo motor the sensor moves left and right, while scanning for objects in a specified area. The device can be controlled using a Toggle switch, which turns the machine on and off. There are three LEDs and a Buzzer placed on the breadboard: the first red LED shows the status based on the Toggle switch, the green LED is turned on while the device is active and searching, and the second red LED blinks depending on the distance measured from the sensor to the detected object. Finally, the Buzzer is used as an alarm, that let's us know we found a target. 

Setup

We can communicate with the Arduino using a free software called Arduino IDE, that let's us upload code to our device. After installation create a new Sketch and paste in the code given. If you followed the circuit diagram provided you're all set! However, if you used different ports make sure you also change the variables holding the Pin numbers. After connecting your Arduino to your PC using an USB-A to USB-B cable you should be able to see in the bottom right corner something along the lines of Arduino UNO on COM6. Keep your COM number in mind, because you will need it to set up the rest of the code. 
We can also monitor the sensor's readings using a program called Processing 3. After downloading the program, create a new Sketch, and paste in the source code given below. Before running, there are a couple of things that must be changed. First, head over to Line 24 and change the values to your monitor's resolution. A few lines lower, on Line 26 replace the second parameter with your COM number. With that done, you are ready to party! Go back into Arduino IDE and from the top left corner click Upload, and wait a few seconds for the code to get uploaded to your Arduino. After that you can go to Processing and you can start the radar interface. With everything set up correctly the radar's movement and the green lines on your screen should be synced.

Showcase

Video 1: https://www.youtube.com/watch?v=H7krqRXtmUs&list=PLF_prIHOkIhWpnFm8JDy6p6xMlMXVni2M
Video 2: https://www.youtube.com/watch?v=tc6iqRHBJUk&list=PLF_prIHOkIhWpnFm8JDy6p6xMlMXVni2M&index=2

For more information regarding this project, check out this post: 

This project has endless upgrades, I would be interested in hearing your thoughts and ideas on how I could improve this project (please excuse the wiring)! 
If you have any questions feel free to ask, I'll try my best to answer them as quickly as possible. Cheers! 
