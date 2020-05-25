## Model Documentation

---

**Highway Driving**

#### Describe in detail the code model for generating paths

The path planning starts at line 79 of `main.cpp`. First, sensor fusion data is collected and used to track other cars. This is essential in order to safely perform a lane change without hitting other cars that might be on the intended lane. The car checks whether it's close to another car in front of it on the same lane. It does that by selecting the lane the car is driving on right now (line 123), and if it finds another car in front of it within a distance of 30m, it decides that it's close enough to change lanes. Given that the car is able to change lane to its left or its right and there are no other cars on the intended lane within 30m behind or 30m in front of the car, the car changes lane. Otherwise, it decelerates and waits for a lane to free up.