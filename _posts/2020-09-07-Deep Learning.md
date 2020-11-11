---
title:  "Deep Learning"
excerpt: "note"

categories:
  - DL
tags:
  - DL

last_modified_at: 2020-10-01
 
---

# Deep Learning note

## sigmoid and tanh

If I have to predict among 2 categories, it's better to use a sigmoid function. However, A softmax function is mostly used with more than 3 categories. <br>
Sigmoid and Tanh essentially produce non-sparse models because their neurons pretty much always produce an output value. <br>
It can be occured a vanishing gradients problem.


## Relu

Relu function is more faster and has less problem with vanishing gradients problem.

## Cross Entropy

Cross Entropy is usually used with one-hot encoding.

![](/assets/images/post/deep_learning/cross_entropy.svg)

## Gradient Desent

Batch Gradient Descent is too slow to calculate loss value. <br>
Stochastic Gradient Descent is using a part of whole batches. <br>
Local minima problem can be fixed by using SGD. However, It cannot be 100% accurated.

## specify the bounding boxes

y = [1 bx by bh bw 0 0 0 ~]^T <br>

bx and by have to be between 0 and 1. (x,y) cordinate needs to be in grid cell. <br>

bh and bw could be more than 1. (height, width) can be greater than gird cell. <br>

## Adversarial Attack

An adversarial attack consists of subtly modifying an original image in such a way that the changes are almost undetectable to the human eye. The modified image is called an adversarial image, and when submitted to a classifier is misclassified, while the original one is correctly classified. <br> (https://medium.com/onfido-tech/adversarial-attacks-and-defences-for-convolutional-neural-networks-66915ece52e7)

![Explaining and Harnessing Adversarial Examples](/assets/images/post/deep_learning/adversarial_attack.png)


https://arxiv.org/abs/1412.6572
{: .notice--info}