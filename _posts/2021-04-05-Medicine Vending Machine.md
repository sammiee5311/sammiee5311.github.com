---
title:  "Medicine Vending Machine"
excerpt: "Note"

categories:
  - Capston
tags:
  - Capston

last_modified_at: 2020-04-05

classes: wide
  

---

[code](https://github.com/sammiee5311/medicine_vending_machine)

This year is the last year at my university, so my friends and I are going to start a project in order to graduate.<br>

We came up with some ideas for what we are going to make which are ‘smart farm’, ‘traffic accident CCTV and ‘medicine vending machine’. First, we chose a smart farm idea. We had not only built a machine that drives itself but also builds a drone in order to achieve our plan. So we have decided to choose the ‘medicine vending machine’ idea.<br>

Building a medicine vending machine was not easy. Because it has lots of obstacles. One of the obstacles is that selling certain medicines is illegal without the permission of a pharmacist. However, we concluded that people who use the machine that we are going to build can talk to the pharmacist in order to get permission through the camera on it.<br>


<center> <img src="/assets/images/medicine_vending_machine/how_it_works.png" width="720"> </center>

<center> This picture shows that how it works briefly. </center> <br>

Basically, a user can buy either general medicines or external medical supplies (ex, bandage, Tylenol, etc…). The user needs to be talked with a pharmacist in order to buy a general medicine. <br>

If the user pushed the ‘call’ button on the machine screen, the request will be sent to one of the pharmacists who are waiting for the users’ request on the application. Then a pharmacist diagnoses what the user’s medical problems are and chooses the suitable medicines for the user. After that, the user will get medicines from the vending machine.<br>

Other than general medicines, a user can buy without a video call with a pharmacist. <br>


Database we use is MongoDB which is NoSQL so that all data is stored as wide-column. 


medicine table | machine table | order table
:------------: | :-----------: | :-----------:
<img src="/assets/images/medicine_vending_machine/medicine_table.png" width="720">  | <img src="/assets/images/medicine_vending_machine/machine_table.png" width="720"> | <img src="/assets/images/medicine_vending_machine/order_table.png" width="720">

As on the above table, we use medicine, machine and order tables. There is a video table too which we haven't finished yet. <br>

We've made a webpage that allows a user to buy medicines on machine. The webpage was created with nodejs and has 3 main features. <br>
- First, by making a video call, the pharmacist consults with the user and discharges the needed medicine remotely.
- Second, we'll record which medicines sell the most in the area, and we'll use this data in the future.
- Last, The machine recommends using the condition mentioned by the user (Natural Language Processing).

temporary external | temporary main | temporary general 
:------------: | :-----------:  | :-----------:  
<img src="/assets/images/medicine_vending_machine/temporary_web1.png" width="720">  | <img src="/assets/images/medicine_vending_machine/temporary_web0.png" width="720"> | <img src="/assets/images/medicine_vending_machine/temporary_web2.png" width="720">