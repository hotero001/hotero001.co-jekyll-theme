---
layout: post
title: Smart Blinds Automation
---

This is a re-write of a post from March.

During the past few months I have fully immersed myself in writing code and building shit. I built a Rails app that is a jobs board. I wrote small scripts that automate things, like converting an HTML file to csv. I was thinking too small. As I was thinking of cooler projects to build with an increased level of difficulty and pragmatism, I decided to begin the process of building a smart home. I chose to focus first on automating blinds. In essence, converting ordinary blinds to "smart blinds". I have made some headway, but I still have a long way to go until I complete this project. Below is an outline of what I have done so far, and what I still have left to do.

First, allow me to explain "smart blinds". Smart blinds are blinds that can be opened and closed from anywhere in the world, as long as you have access to an internet connected device. More realistically, I aim to open/close my blinds from the couch using my smart phone or ipad. I have purchased a Raspberry pi(RPi), which is a microprocessor that can connect to the internet via ethernet or wifi dongle. I have set the RPi as a wifi access point, which is not as trivial as it sounds, and it is now able to connect to the internet. The wifi connection has been spotty so far, so I will likely stick to ethernet. Next, I purchased a 5V stepper motor which is actuated by the Raspberry pi. I have written a program in Python that spins the stepper motor in either direction and stops when you send the proper command. This is where I am at for the moment. 

The next steps are: 1) Build a Rails app and iOS app that can connect to the RPi, and submit the commands to spin the motor in either direction. I have spent the past month learning how to build iOS apps in Swift so that I can accomplish this. I may write an Android app for this as well, since i have an Android phone.

2) Create a CAD file for a piece that hooks onto the stepper motor on one end, and hooks on to the blinds' rotating wand on the other end. Then, I will have this piece manufactured by a 3-D printer. I have significant work experience designing things on CAD programs such as solidworks/autodesk inventor, so this step should not be very difficult.

3) System integration & Testing. Mount the RPi to the blinds and connect the pieces together. The RPi will need to be placed in a case to prevent ESD. Lastly, test the system with both the web and mobile apps. One potential concern is the temperature of the stepper motor. Having worked with other electrically actuated components in the past, they have a tendency to get hot, and this can reduce the life span of the component, or pose safety concerns. As such, a heat sink may need to be attached to the stepper motor to prevent elevated temperatures. 

4) Enjoy!

