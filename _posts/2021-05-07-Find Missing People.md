---
title:  "Find Missing People"
excerpt: "diary"

categories:
  - project
tags:
  - project

last_modified_at: 2020-05-09

classes: wide
  

---

[code](https://github.com/sammiee5311/find_missing_people)

After reading a few articles about the missing people, I've started this project thinking how to find the missing people more effectively. <br>

In addition to CCTV cameras, cmaeras of self-driving car which is one of the main technologies of the Fourth Industrial Revolution era are used to compare the face of the person registered on the server and find the missing person. <br>

I used Python for a main langauage, JavaScript for a few web features, Django framework and PostgreSQL for a database. <br>

I created a website that allows people to register and request missing people in order to access easily and visually. <br>



### Sequence

- A person requests on the website.
- Any admin checks the request and accepts it or not.
- If an admin accepts the request, the request form is registered on the website, including a picture of a missing person. [1]
- Anyone who has a self-driving car can choose either collecting images of missing people or not.
- When the self-driving car is on standby, it finds itself by comparing the face in the picture taken by the camera with the missing person.
- If it finds the same face on the server, the picture will be sent to the server, and the person who requests can check whether it's correct or not. [2]


1 | 2 |
:------------: | :-----------: |
<img src="/assets/images/find_missing_people/psersonInfo.png" width="720">  | <img src="/assets/images/find_missing_people/dashboard.gif" width="720"> |

As you can see above images, the first one is a page which shows missing people info and descriptions. ([All the images of people on the website is not real people](https://www.thispersondoesnotexist.com/)
) <br>

On the second image, it is a dashboard where people can check their requests and check the self-driving car took images well enough or not.

<center> <img src="/assets/images/find_missing_people/map.gif" width="720"> </center>
<center> People can also check missing people by searching on map. </center>

<br>
    
<center> <img src="/assets/images/find_missing_people/test.gif" width="720"> </center>

I've just combined it with my self-driving car which I made with a raspberry-pi to show how would be worked with a self-driving car.

