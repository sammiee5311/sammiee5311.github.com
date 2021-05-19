---
title:  "[raspi]Self-Driving"
excerpt: "diary"

categories:
  - raspi
tags:
  - raspi
  - diary

classes: wide

last_modified_at: 2020-11-18
 
---

# Self Driving

https://github.com/sammiee5311/raspberry_pi/tree/master/self_driving_car

### First Try

I tried to use a camera to detect the tape on the floor so that the machine can measure which direction has to be selected. <br>

<p float="left">
  <img src="/assets/images/post/raspberry_pi/self_driving/first_try/original.jpg" width="450" />
  <img src="/assets/images/post/raspberry_pi/self_driving/first_try/canny.jpg" width="450" /> 
</p>


First, I used a canny edge detector to change the image and then used a hough line transform to extract the feature of the line on the image. <br>

And then, the only region I wanted to detect was half of the image's height. So I combined the original image with the image of the lines that are already detected.

<p float="left">
  <img src="/assets/images/post/raspberry_pi/self_driving/first_try/lines.jpg" width="450" />
  <img src="/assets/images/post/raspberry_pi/self_driving/first_try/image.jpg" width="450" /> 
</p>

Lastly, the Raspberry Pi will calculate # of left lines and right lines in order to move correctly. <br>

If there are more left lines than right lines, the car will move to the right side. (The accuracy was not that bad, but I didn’t have enough power to move all 4 of the motors. So it moves a little weirdly) <br>

But I wanted to use deep learning with Raspberry Pi, so I tried to change the way. <br>

### Second Try

I’ve taken plenty of car course pictures (approximately 2000) to make the machine learn by using deep learning. <br>

First, a ps4 controller was used because the steering angle could be obtained in a wider range rather than using a keyboard. I could get values of angle between -0.5 and 0.5. <br>

And then, I coded with OpenCV to save the pictures and the steering angle in X, y lists while the car moving. I made the machine be trained with these X(images), y(steering angles) datasets. <br>
 
<center><img src="/assets/images/post/raspberry_pi/self_driving/second_try/network_architecture.png" width="450" height="450"></center>
<center>(https://developer.nvidia.com/blog/deep-learning-self-driving-cars/)</center>

I used an NVIDIA network architecture to train my model. <br>

But my model’s accuracy was only around 50%. I figured out the images and steering angle was not the right time. <br>

The problem was there was a delay between saving pictures and putting steering angles to X, y lists. <br>

So I changed the plan. <br>

### Thrid Try

My Raspberry Pi’s SD card was corrupted, so I had to format my SD card and re-install the OS. It took time to install OpenCV and other libraries again. <br>

This time, I tried to classify left, right, and forward in order to get better accuracy. <br>

I used the same architecture as an NVIDIA architecture. <br>

#### Last 3 results
+ loss: 0.3880 - acc: 0.8750 - val_loss: 0.3680 - val_acc: 0.8875
+ loss: 0.3339 - acc: 0.8969 - val_loss: 0.3208 - val_acc: 0.9250
+ loss: 0.3318 - acc: 0.9062 - val_loss: 0.5883 - val_acc: 0.7250
{: .notice--info}

I got around 85% of accuracy, 80% of validation accuracy, and 0.35 of validation loss. <br>

However, I tried to use TensorFlow in my Raspberry Pi to predict the direction of the car. <br>

It was too slow to load the model and predict the value, so I decided to use my computer due to the fact that my Raspberry Pi is too slow to use deep learning. <br>


### Fourth try

I had been studying socket in order to send & receive data from computer to Raspberry Pi in both ways. <br>

Every frame on Raspberry Pi will be sent to the computer by using a socket. Then saving images and steering angle in X, y lists on the computer. <br>

I’ve tried with around 1000 pictures. However, I had something wrong with the pi-camera. So I had to try another way. <br>


### Fifth try

I watched one of the videos that is about self-driving. One of the YouTubers(Murtaza workshop) put white paper on tape so the difference between the floor and the tape will be more clearly seen. <br>

I’ve got approximately 70% of accuracy but still, it needs to be higher accuracy in order to not move out of the lines. <br>

I have to adjust the data by myself then it will get higher accuracy. <br>

<center><img src="/assets/images/post/raspberry_pi/self_driving/fifth_try/car.gif" width="450" height="450"></center>

It worked pretty well.
