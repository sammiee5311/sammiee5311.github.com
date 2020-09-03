---
title:  "Natural Language Processing"
excerpt: ""

categories:
  - NLP
tags:
  - NLP

pulish: False
  
last_modified_at: 2020-09-05
 
---

## RNN

The problem is that the gradient of the reccurent gate is multiplicative while backpropagation with small value of loss(ex. 0.001) or high value of loss(ex.1.5). It means that there has an expoential function or vanishing gradient problem. <br>

In order not to destroy whole internal states we've just calculated, it is better to pad '0' in the beginning of embedded texts.(not always) <br>

When it needs to be truncated, it is better to truncate at the end of embedded texts due to lose essential information of ditinguishing the text's sentiment.