---
title:  "Reinforcement Learning"
excerpt: "note"

categories:
  - RL
tags:
  - RL

last_modified_at: 2020-10-07
 
---

# Reinforcement Learning note

## Intersection Over Union

y_pred=model.predict(X_test)  #Your predictions on the test dataset
y_pred_thresholded = y_pred > 0.5  #If predictions are not binary, then convert them to binary by thresholding

intersection = np.logical_and(y_test, y_pred_thresholded)  #Intersection is just a logical and.
union = np.logical_or(y_test, y_pred_thresholded) #Union is a logical or
iou_score = np.sum(intersection) / np.sum(union)
print("IoU socre is: ", iou_score)