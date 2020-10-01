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

Sigmoid and Tanh essentially produce non-sparse models because their neurons pretty much always produce an output value. <br>
It can be occured vanishing gradients problem.


## specify the bounding boxes

y = [1 bx by bh bw 0 0 0 ~]^T <br>

bx and by have to be between 0 and 1. (x,y) cordinate needs to be in grid cell. <br>

bh and bw could be more than 1. (height, width) can be greater than gird cell. <br>

## Adversarial Attack

Adversarial machine learning is a machine learning technique that attempts to fool models by supplying deceptive input. (wikipeida)