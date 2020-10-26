---
title:  "[q_learning]Number Game"
excerpt: "diary"

categories:
  - q learning
tags:
  - q learning
  - diary

classes: wide

last_modified_at: 2020-10-18
 
---

# Number game

I've set values like below.


``` python
EPISODES = 15000        MOVE_PENALTY = -1        ANSWER_REWARD = 50      HALF_REWARD = 20
epsilon = 0.9           EPS_DECAY = 0.99998      SHOW_EVERY = 500         STEP = 200
LEARNING_RATE = 0.001   DISCOUNT = 0.95         
```

It basically guess the numbers(2 digits) that are randomly set between 0 to 9. <br>

The q table is 2 dimension which is included tuple number(observation) and each number of actions' values. <br>

There are 5 actions that are 'minus one', 'plus one' and 'stay' each digits except 'stay'. <br> 


<center> <img src="/assets/images/q_learning/Figure_1.png"> </center>
<center>(average of episode rewards)</center>


I have learnt q learning from **sentex** Youtuber
{: .notice--info}