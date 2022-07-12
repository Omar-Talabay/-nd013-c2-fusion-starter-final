# Writeup: Track 3D-Objects Over Time

Please use this starter template to answer the following questions:

### 1. Write a short recap of the four tracking steps and what you implemented there (filter, track management, association, camera fusion). Which results did you achieve? Which part of the project was most difficult for you to complete, and why?

The projects starts with implementing a simple Kalman filter as Filter class. Covariance matrices are retrieved and predict/update functions are filled.
RMSE is .35 as appears in the following figure:

<img src="./Figure_1_2.png" width="400" height="300" />

To enable multi-traking, track management and association are essetial. 

* Track management: This class is responsible for adding/removing tracks and objects to the track list comming from measurments. Dealing with unassigned tracks and deleting old tracks or tracks that are bellow a certain threshold is dealt with. Also adjusting track score for unassigned track is implemented. Also coordinates transformation from/to vehicles is a part of this module.

* Association: Every time a measurment is received and identified, linking objects with previously detected ones is the main part of this module. What follows is the main implemented parts:
1 - Mahalanobis distance is implemented to compute the distance between detected measurements and already available objects in tracks. 
2 - gating function: to reduce the association time complexity.
3 - associate function: to compute the distance between objects in tracks and objects in measurements.




### 2. Do you see any benefits in camera-lidar fusion compared to lidar-only tracking (in theory and in your concrete results)? 


### 3. Which challenges will a sensor fusion system face in real-life scenarios? Did you see any of these challenges in the project?


### 4. Can you think of ways to improve your tracking results in the future?

