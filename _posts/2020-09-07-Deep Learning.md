---
title:  "Deep Learning"
excerpt: "note"

categories:
  - DL
tags:
  - DL

last_modified_at: 2020-09-07
 
---

# Deep Learning note

## specify the bounding boxes

y = [1 bx by bh bw 0 0 0 ~]^T <br>

bx and by have to be between 0 and 1. (x,y) cordinate needs to be in grid cell. <br>

bh and bw could be more than 1. (height, width) can be greater than gird cell. <br>