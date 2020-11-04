---
title:  "[q_learning]Flappy Bird"
excerpt: "diary"

categories:
  - q learning
tags:
  - q learning
  - diary

classes: wide

last_modified_at: 2020-11-04
 
---

# Number game

I've set values like below.


``` python
EPISODES = 100000       COLLISION_PENALTY = 800    POINT_REWARD = 50      ALIVE_REWARD = 1
epsilon = 0.9           EPS_DECAY = 0.99998        STEP = 500             LEARNING_RATE = 0.3
DISCOUNT = 0.95         
```

<center> <img src="/assets/images/q_learning/Figure_2.png"> </center>
<center>(average of episode rewards)</center>


I modified flappy bird game on https://github.com/Anish-Malla/Flappy-birds-game-using-pygame
{: .notice--info}