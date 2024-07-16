# Arduino Radar System

Building a home-made radar system using an Ultrasound sensor and an Arduino UNO.

![showcase](https://github.com/user-attachments/assets/20dbd982-e033-4804-8eea-e090cab68c40)

## Introduction

With the help of a micro servo motor the sensor moves left and right, while scanning for objects in a specified area. The device can be controlled using a **Toggle switch**, which turns the machine on and off. There are three **LED**'s and a **Buzzer** placed on the breadboard: the first red LED shows the status based on the Toggle switch, the green LED is turned on while the device is active and searching, and the second red LED blinks depending on the distance measured from the sensor to the detected object. Finally, the Buzzer is used as an alarm, that let's us know we found a target.

## Components

* **1x** [9G Micro Servo](https://www.amazon.com/Sipytoph-Helicopter-Airplane-Walking-Control/dp/B09185SC1W/ref=sr_1_13?dib=eyJ2IjoiMSJ9.tVLqy2AGpupwOFNupo-YTuoTttEjBv2ctPZik0NvQ9EY0iSztVtsF2rGLh1AzqoPSp1U_Wnv0ZLKdLcgW30tMrIIdLXxx0FNB8tOncqhG5J_SqNkvEULqbQQMMDRp0iZjzBwTOO_Q2dUDBPN43PFrH3NHq-VUdudmRLXFH1eIDWVxE8WnzaGKcwCUqsok6vRSvZvFYONLeHoGVtG49_W56nOgjjyJwU4OwdMMwZksQ_oxMTMZnxucVxWGY5bW0XN8BVzilRD9Ih7AiQBIckqmlwTzFkhItdQSnZxdVp6vmo.8Ou7Jp_t7_afKpZYLmrM8C3qKaquPQ5z-acKNuPuc8U&dib_tag=se&keywords=sg90%2B9g%2Bmicro%2Bservo&qid=1721123630&sr=8-13&th=1)
* **4x** [220 Ohm Resistors](https://www.amazon.com/EDGELEC-Resistor-Tolerance-Multiple-Resistance/dp/B07QK9ZBVZ/ref=sr_1_3?dib=eyJ2IjoiMSJ9.48C-Ove2hC0iqcDJWqOBW0Ym2y_kNHj8NmJQZB-_us_d_Y2U3Mei1LQsdqeGlHxAOL_yqpEQGQHEay917onU1Snhys6R-f4QrB6YwhLyu-pV0XFcB9a8FBAzk3uxQkB-QeMKssnn8-o_5hfJBXbmbCukGSoU7t6oBcBj2v4o068X5DLuNnWkQ3s2cIjC0T5-pJ9vm6MZoEkd-rxX9uMocnWWnO1UkTZRG0cW9eWLmiA.my682eInl2JCE44AhL95ixHIdhNRGPn4yrdFyjhLCt0&dib_tag=se&keywords=220%2Bohm%2Bresistor&qid=1721123739&sr=8-3&th=1)
* **1x** [1k Ohm Resistor](https://www.amazon.com/California-JOS-Carbon-Resistor-Tolerance/dp/B0BR66ZN6B/ref=sr_1_3?dib=eyJ2IjoiMSJ9.sjCrXtEr0PMGKZXQLPwE43Cm6Wuj_WtcdUxQqil3rZKsZCgpkZt-IB7HoRMDPFJcoswO2Uk0H--0JcokTP_F8y62pPJYPLZVKrqhKFDLf6aSjf_ArcWDYUTjf6oJ39qh3zOZhNvWW4iFF-qfksisUQwZ-rP-fDrk6E5f5wuiSsk68f-Qhqpj5BV5U4n4TpqwLWK_L2kDlll2fCG363nzoj8U42UiGgE8cFLLLAdOpSE.KIq2jWvPuqMAdxSxDxpyttI_hQKgC60Y7gxmX35z09A&dib_tag=se&keywords=1k+ohm+resistor&qid=1721123787&sr=8-3)
* **1x** [Arduino UNO](https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6?th=1)
* **1x** [HC-SR04 Ultrasonic sensor](https://www.amazon.com/CUQI-Ultrasonic-Measuring-Transmitter-Compatible/dp/B092D2DS1Y/ref=sr_1_7?dib=eyJ2IjoiMSJ9.e5Yfpkja9gNArv99GdcfIbPkHEwnA5_v-S2dX3lHPU3MyNznCsGAeUrd-5fU9Rr--v6lKcSiP1qtwKGtZ4U6iIyEu3tQeQDcjDoBF8Rr-DnlnOqHPWsWJkx1OTDYJXcwu1JHqTeM9I0GQHHG2UUBuqZrGGQZTqGoBZobHn-WX68uAJtgftcVYLoN-gkkyDb20tqUkWmTd4heQlxdsH6gtfo9aJEISmw9hs7DgNmwgiu4kvEQuT42iQbJKSwX5lm0._BGqBfyM2MFj0nQTpUEkfFggIofOIGWG7vi_lSd9RQw&dib_tag=se&keywords=HC-SR04+ultrasonic+sensor&qid=1721123908&s=electronics&sr=1-7)
* **1x** [Buzzer](https://www.amazon.com/Gikfun-Terminals-Passive-Electronic-Arduino/dp/B01GJLE5BS/ref=sr_1_6?dib=eyJ2IjoiMSJ9.xguNP2bafm6PIldIUszcpPI9f2cyz4-uGdxia46YmzQ2paZ9-BmEPre13kPCBvFIq6vTVNJP3l6tRu9PIvQ8E0_Iu-x77kIAaSiZILk0IEuKJYCL0bFfFLpsZJANQaI0zLSrC7phT9GdcVwmDtpsTXpH6hBRxbXUARJKB-fi0od2LyrqsNp-ssiOq_RYsYm155WKhivntVNcnb8sViuA2I6B04OFFhWPLbvhTOxKXfs.5hHxn7kvXj48BaoaZFFDG9ssFbCOnrzk-9IBletQgeE&dib_tag=se&keywords=arduino+buzzer&qid=1721123964&sr=8-6)
* **25x** [Jumper wires](https://www.amazon.com/EDGELEC-Breadboard-Optional-Assorted-Multicolored/dp/B07GD2BWPY/ref=sr_1_4?dib=eyJ2IjoiMSJ9.tjHxIQLJsk16_0YVtUGN6bYgnUPWn3fCzYUZwBtpSZaF0zysY3u40uHgMv-5D_xi3SSveAixO_v7-PG8AAOKg4k6CcE-VPeviYUDrt7wBOUSk8jVDe4HiIdXlm2vSIwaUpEJ7XPLfkQvjyz8ulufYAi10GFh_WkEfFsE4JSfxN__bJnGcOrf7PFd_oEVBJtOWv6e5tCSjyDF5zgmfTAdcsiDGJ9ku7LJb3mxwIm4R00.k_0oqUoKw4kngT7_p90ohlo8RJzZPMudwB1OqUdW-PU&dib_tag=se&keywords=jumper+wires&qid=1721124000&sr=8-4)
* **1x** [USB 2.0 Cable Type A/B](https://www.amazon.com/Amazon-Basics-External-Gold-Plated-Connectors/dp/B00NH13DV2)
* **2x** [Red LEDs](https://www.amazon.com/OWOFYDR-diffused-Electronic-Component-Indicator/dp/B09B9BYS8V/ref=sr_1_44?dib=eyJ2IjoiMSJ9.1GA_RFabAsi0c0X-4kwArkVI6BtmSWlWVSXkxYoqdkzgexkgtHKch3tQbV11J8oPL7BOHIWkDYzo4fdNXZvtTyF8HwF2wGdMRojluGlxkFttevJf3-zsCwcoz3Vd_X7q8Lo52UE0w-uqhKM-Q59BNC_j8OuXHNLxrMD3Wpyzsgr5aH2U0qwAClJAdUVUZIMo1zuOW3pOR94jdL6HfmZq8J2UnatpmBqnavFMp3KSjIhpEqh6cEqqdML8GQA6eLpsfChxB_ArKNeY4R61mmgxt3EnVEluyloGXWc5rZfgvrE.qVRyBYPE093WQImwLau45kxiddswppi1j_YN315Q5Vg&dib_tag=se&keywords=green%2Bled%2Blights&qid=1721124115&sr=8-44&th=1)
* **1x** [Green LED](https://www.amazon.com/OWOFYDR-diffused-Electronic-Component-Indicator/dp/B09B9FD3Z3/ref=sr_1_44?dib=eyJ2IjoiMSJ9.1GA_RFabAsi0c0X-4kwArkVI6BtmSWlWVSXkxYoqdkzgexkgtHKch3tQbV11J8oPL7BOHIWkDYzo4fdNXZvtTyF8HwF2wGdMRojluGlxkFttevJf3-zsCwcoz3Vd_X7q8Lo52UE0w-uqhKM-Q59BNC_j8OuXHNLxrMD3Wpyzsgr5aH2U0qwAClJAdUVUZIMo1zuOW3pOR94jdL6HfmZq8J2UnatpmBqnavFMp3KSjIhpEqh6cEqqdML8GQA6eLpsfChxB_ArKNeY4R61mmgxt3EnVEluyloGXWc5rZfgvrE.qVRyBYPE093WQImwLau45kxiddswppi1j_YN315Q5Vg&dib_tag=se&keywords=green%2Bled%2Blights&qid=1721124115&sr=8-44&th=1)
* **1x** [Slide switch](https://www.amazon.com/WOWOONE-Vertical-Switch-Position-CYT1107/dp/B08JYV8HZ7/ref=zg_bs_g_18945323011_d_sccl_9/147-2167741-4085639?psc=1)
  
## Setup

We can communicate with the Arduino using a free software called **Arduino IDE**, that let's us upload code to our device. After installation create a new Sketch and paste in the code given. If you followed the circuit diagram provided you're all set! However, if you used different ports make sure you also change the variables holding the Pin numbers. After connecting your Arduino to your PC using an **USB-A** to **USB-B** cable you should be able to see in the bottom right corner something along the lines of `Arduino UNO on COM6`. Keep your COM number in mind, because you will need it to set up the rest of the code.

We can also monitor the sensor's readings using a program called **Processing**. After downloading the program, create a new Sketch, and paste in the source code given below. Before running, there are a couple of things that must be changed. First, head over to **Line 24** and change the values to your monitor's resolution. A few lines lower, on **Line 26** replace the second parameter with your COM number. With that done, you are ready to party! Go back into Arduino IDE and in the top left corner click *Upload*, and wait a few seconds for the code to get uploaded to your Arduino. After that you can go back into Processing and you can start the radar interface. With everything set up correctly the radar's movement and the green lines on your screen should be synced.

## Showcase

[Video 1](https://www.youtube.com/watch?v=H7krqRXtmUs&list=PLF_prIHOkIhWpnFm8JDy6p6xMlMXVni2M)

[Video 2](https://www.youtube.com/watch?v=tc6iqRHBJUk&list=PLF_prIHOkIhWpnFm8JDy6p6xMlMXVni2M&index=2)

For more information regarding this project, check out [this](https://projecthub.arduino.cc) post.

This project has endless upgrades, I would be interested in hearing your thoughts and ideas on how I could improve this project (please excuse the wiring)! 
If you have any questions feel free to ask, I'll try my best to answer them as quickly as possible. Cheers! 
