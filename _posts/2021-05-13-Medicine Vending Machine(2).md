---
title:  "Medicine Vending Machine(2)"
excerpt: "diary"

categories:
  - Capston
tags:
  - Capston

last_modified_at: 2020-06-01

classes: wide
  

---

[code](https://github.com/sammiee5311/medicine_vending_machine)

[medicine vending machine](https://sammiee5311.github.io/capston/Medicine-Vending-Machine/)

We used an Arduino Mega, a Raspberry Pi 4, motors, a microphone, a touch screen, and lots of cables. In order to control all the 7 motors, we had to manage voltage well. <br>

- First, we put 5v to the Raspberry Pi 4 and touch screen each. 
- Second, we put 5v to the Arduino mega and connect it to the Raspberry Pi 4 to control it.
- After that, we used one more 5v and put it on a breadboard with all motors to cover all the motors.

We finally manage to build a prototype of our machine. <br>

 
| Prototype | 
| :------------: |
| <img src="/assets/images/medicine_vending_machine/prototype_test.gif">|


After few weeks, We've ordered acrylic plates so that the machine will be looked better. <br>

We had few issues which are a touchscreen issue, a motor issue, etc. The reason why a touchscreen issue was the worst issue is that we've tried to rotate the screen 90 degrees, but it does not work quite well. <br>

We could rotate the screen but not the touch calibrations in order to sync the screen location and the touch location. The Raspberry Pi 4’ booting was only available with CLI. So we have no choice to reformat the Raspberry Pi 4. <br>

In a Few days, The touchscreen worked very well. <br>


This is the result that builds with acrylic plates <br>


| Completed machine | Completed machine |
| :------------: | :------------: |
| <img src="/assets/images/medicine_vending_machine/machine0.jpg"> | <img src="/assets/images/medicine_vending_machine/machine1.jpg"> |