---
title:  "[raspi]Self-Driving (2)"
excerpt: "diary"

categories:
  - raspi
tags:
  - raspi
  - diary

classes: wide

last_modified_at: 2020-12-01
 
---

# Self Driving [(code)](https://github.com/sammiee5311/raspberry_pi/tree/master/self_driving_car)

[self-driving(1)](https://sammiee5311.github.io/raspi/Raspi-Self-Driving/)

### measuring the distance between the car and any objects.

I added a ultrasonic module on my raspberry pi so that it will be stopped if there is any wall in front of it.

### yolov3 object detection

I tried to detect an object with yolov3 and used one of the statues which is at my house. <br>

<center><img src="/assets/images/post/raspberry_pi/self_driving/yolo/lizard.jpg" width="450" height="450"></center>
this is the picture of the statue.
{: .notice--info}


<p float="left">
  <img src="/assets/images/post/raspberry_pi/self_driving/yolo/training_01.jpg" width="450" />
  <img src="/assets/images/post/raspberry_pi/self_driving/yolo/training_03.jpg" width="450" /> 
</p>
Those are some of pictures which have been used when yolov3 is trained.
{: .notice--info}

It detects well because I've taken pictures over 500 pictures and trained it over 8 hours. <br>

However, It was slow in order to detect an object and get the distance as well. <br>

### yolov3-tiny object detection

It worked quite well with yolov3-tiny to detect the statue and get the prediction of steering values.

<center><img src="/assets/images/post/raspberry_pi/self_driving/yolo/object_detection.gif" width="450" height="450"></center>
