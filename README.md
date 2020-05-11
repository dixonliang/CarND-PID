# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

## Overview

This is quick summary of the developing a PID controller and tuning the parameters for the Udacity Self Driving Car ND. A template was given where we had to calculate the following error which I did by using the following equation from which where were given the the CTE (cross track error). The below was then used to calculate the steering angle between [-1,1]. 

```shell
double PID::TotalError() {
  	return -(Kp * p_error) - (Kd * d_error) - (Ki * i_error);
```

We had to choose parameters to begin which I did using a qualiatative measuring from the simulator. Given the assignment, there was not a minimum speed so I chose a realtively low throtte of 0.1 which allowed the car enough time to make changes. 

```shell
PID pid; // initialize pid
double kp = 0.10;
double ki = 0.0001;
double kd = 3.0;
pid.Init(kp, ki, kd);
```
In a future implementation, the parameters could be better tuned using something like Twiddle as well as behavior could be adjusted to lower the throttle when the error approaches a certain threshold. Currently, it does come close to driving off the road on sharp turns, but manages to stay on the track throughout the entire simulation. 
