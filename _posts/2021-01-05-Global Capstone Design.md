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

We used Computer, Jetson nano, two motors, a button,  two cameras, a speaker, Yolov3-tiny, WEB, AWS, and DB. <br>

## System works

While a camera that sticks on the Jetson nano is running, users can put an object in the machine. Once the machine detects the object, the image which is captured by Jetson nano will be sent to a computer in order to process Convolutional Neural Network. <br>

We have tried to use Jetson nano to calculate the model, but it was slow due to Jetson nano’s threshold.

We used Yolov3-tiny to detect and classify the object. The result from the computer will be sent back to Jetson nano. ( Jetson nano and Computer communicate by using socket. ) <br>

The machine has a screen and a speaker which shows and tells you how to recycle properly. After classifying what the object is, the machine will automatically divide it into 3 classes. <br>

The object will be fell down depends on classes. There is a button that lets the machine knows that users stop recycling. <br>

When a user pushes the button, the other camera will be turned on and waiting for the QR code. The QR code is given when users register through the WEB or application. It contains a unique ID. Once the QR code is detected, the reward will be added to DATABASE. <br>

<center> <img src="/assets/images/capstone/system_design.png"> </center>
<center>System Design</center>

## Model

<center> <img src="/assets/images/capstone/model_img.png"> </center>
<center>Model</center>
<br>

This is our basic model that we have built. We could make it with 3d printer, however, we did not have enough time to print the whole board of the machine. <br>

Instead, we used acrylic plates in order to build it.


## Demonstraion

<center> <img src="/assets/images/capstone/demonstration_1.gif"> </center>
<center>Demonstrain I</center>
<br>
As you can see, It detects the object and fell down in the right bin.

<center> <img src="/assets/images/capstone/demonstration_2.gif"> </center>
<center>Demonstrain II</center>
<br>
On this image, It detects wheather it is available to recycle or not.  

## Procedures
1.    Put any recycling items in the machine. <br>
2.    Wait until the machine detect whether it can be recycled or not.  <br>
3.    If the item is available to recycle, it will fell down in the trash bin. <br>
4.    Get the reward depends on how many you put and which object you put. <br>


## What i felt about Global Capstone Design

It was a good experience for me to do the project with other people. I’ve never done a project with someone so not only make better but also having fun with them. <br>

I wish I could have more opportunities like this.