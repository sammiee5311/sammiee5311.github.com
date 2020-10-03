---
title:  "[raspi]Self-Driving"
excerpt: "diary"

categories:
  - raspi
tags:
  - raspi
  - diary

classes: wide

last_modified_at: 2020-10-03
 
---

# Self Driving

### First Try

I've tried to use a camera to detect the tape on the floor so that the machine can measure which direction has to be selected. <br>

<p float="left">
  <img src="/assets/images/post/raspberry_pi/self_driving/first_try/original.jpg" width="450" />
  <img src="/assets/images/post/raspberry_pi/self_driving/first_try/canny.jpg" width="450" /> 
</p>


First, I've used a canny edge detector to change the image and then used a hough line transform to extract the feature of the line on the image. <br>

And then, the only region I wanted to detect was half of the image's height. So I've combined the original image with the image of the lines that are already detected.

<p float="left">
  <img src="/assets/images/post/raspberry_pi/self_driving/first_try/lines.jpg" width="450" />
  <img src="/assets/images/post/raspberry_pi/self_driving/first_try/image.jpg" width="450" /> 
</p>

Lastly, the raspberry pi will calculate # of left lines and right lines in order to move correctly. <br

If there are more left lines than right lines, the car will move to right side. (The accuracy was not that bad but I didn't have enough power to move the all 4 of motors. so it moves little weirdly) <br>

But I wanted to use a deep learning with raspberry pi so I tried to change the way.

### Second Try

I've taken a plenty of car course pictures (approximately 2000) to make the machine learn by using a deep learning. <br>

First, The ps4 controller was used because the steering angle could be obtained in a wider range rather than using a keyboard. I could get values of angle between -0.5 and 0.5. <br>

And then, I've coded with OpenCV to save the pictures and the steering angle in X,y lists while the car moving. I made the machine be trained with these X(images), y(steering angles) datasets. <br>

<center><img src="/assets/images/post/raspberry_pi/self_driving/second_try/network_architecture.png" width="450" height="450"></center>
<center>(https://developer.nvidia.com/blog/deep-learning-self-driving-cars/)</center>

I've used a nvidia network architecture to train my model. <br>

But my model's accuracy was only around 50%. I've figured it out the images and steering angle were not right time. <br>

The problem was there was a delay between saving picture and putting steering angle to X,y lists. <br>

So I've changed the plan.

### Thrid Try

My raspberry pi's sd card was corrupted so I had to format my sd card and re-install the os. It took time to install opencv and other libraries again. <br>

This time, I tried to classify left,right and forward in order to get better accuracy. <br>

I've used same architecture as a nvidia architecture. <br>

#### Last 3 result
loss: 0.3880 - acc: 0.8750 - val_loss: 0.3680 - val_acc: 0.8875
loss: 0.3339 - acc: 0.8969 - val_loss: 0.3208 - val_acc: 0.9250
loss: 0.3318 - acc: 0.9062 - val_loss: 0.5883 - val_acc: 0.7250
{: .notice--info}

I've got around 85% of accuracy, 80% of validation accuracy and 35% of validation loss. <br>

However, I've tried to use tensorflow in my raspberry pi to predict a direction of the car. <br>

It was slow to load the model and predict the value so I've decided to use my computer due to the fact that raspberry pi is slow to use deep learning. <br> 


### Fourth try

