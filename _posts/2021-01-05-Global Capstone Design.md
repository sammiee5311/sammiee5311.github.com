---
title:  "Global Capstone Design"
excerpt: "Note"

categories:
  - Capston
tags:
  - Capston
  
last_modified_at: 2020-01-05

---

## Topic 

Sustainable living in the New Normal

## Motivation

COVID-19 impacts on the recycling industry. Nowadays, a number of people order delivery food more than before due to the corona-virus. <br>

It is an important thing that people should recycle better for sustainable living. <br>

So we’ve decided to build a machine that automatically sorts out recyclables and then gives rewards to people. <br>

We used Computer, Jetson nano, two motors, a button, two cameras, speaker, Yolov3-tiny, WEB, AWS and DB. <br>

## System works

While a camera that sticks on the Jetson nano is running, users can put an object in the machine. Once the machine detects the object, the image which is captured by Jetson nano will be sent to computer in order to process Convolutional Neural Network. <br>

We have tried to use Jetson nano to calculate the model but it was slow due to Jetson nano's threshold. <br>

We used Yolov3-tiny to detect and classify the object. The result from the computer will be sent back to Jetson nano. ( Jetson nano and Computer communicate by using socket. ) <br>

The machine has a screen and a speaker which shows and tells you how to recycle properly. After classifying what the object is, Machine will automatically divide into 3 classes. <br>

The object will be fell down depends on classes. There is a button which lets the machine knows that users stop recycling. <br>

When user pushes the button,  the other camera will be turned on and waiting for the QR code. The QR code is given when users register through the WEB or application. It contains the unique ID. Once the QR code is detected, the reward will be added on DATABASE.

<center> <img src="/assets/images/capstone/system_design.png"> </center>
<center>System Design</center>

## Procedures
1.    Put any recycling items in the machine. <br>
2.    Wait until the machine detect whether it can be recycled or not.  <br>
3.    If the item is available to recycle, it will fell down in the trash bin. <br>
4.    Get the reward depends on how many you put and which object you put. <br>

## What i felt about Global Capstone Design

It was a good experience to me to do project with other people. I've never done project with somone so not only make better but also having fun with them. <br>

I wish I could have more opportunities like this.