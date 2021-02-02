---
title:  "[q_learning]Snake"
excerpt: "diary"

categories:
  - q learning
tags:
  - q learning
  - diary

classes: wide
  
last_modified_at: 2020-01-31

---

# Snake [(code)](https://github.com/sammiee5311/reinforcement_learning/tree/main/snake)

Firstly, I've used an observation as differences between coordinates of fruit and snake head. However, It was not working well this observation and also I wanted to try with deep learning with reinforcement learning. <br>

So I searched some of youtube videos that showed how to use CNN with q learning. There is [Python Enginner](https://www.youtube.com/channel/UCbXgNpp0jedKWcQiULLbDTA) Youtuber. <br>

I've learnt from him a lot about Deep Q Learning. So I refered to his code. <br>

After I learned from him, I used the observations same as him and it worked out well.

The observations are 4 directions of danger areas, current direction, 4 directions of fruit. (Meaning of 4 directions is that left, right, down and up from the snake head) <br>

<center> <img src="/assets/images/q_learning/snake_test.gif"> </center>
<center>(result)</center>

<center> <img src="/assets/images/q_learning/Figure_3.png"> </center>
<center>(average of episode rewards)</center>