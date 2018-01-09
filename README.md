# **Project: PID Controller**
[![Udacity - Self-Driving Car Engineer NanoDegree Program](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)


## Overview
This repository contains all the codes and reflection that required for completing project. The goal of this project is to implement a PID controller that make car drive the track of given simulator.

Build instruction and dependency of this project is identical to [upstream repository](https://github.com/udacity/CarND-PID-Control-Project) which is the starter code repository of udacity.


## Reflection

### The effect each of the P, I, D components

In this project, we are trying to calculate steering angle with `CTE`(cross track error) which is distance between vehicle and reference trajectory. Followings are the effect of each `P`, `I`, `D` component and expectation from them.

 - `P` : `P` stands for `proportional`. `P` controller steers vehicle `proportionally` with distance between vehicle and center line rather than fixed amount of angle. But, only with `P` component the vehicle can be crooked when it reaches reference trajectory and repeatedly overshoot the desired trajectory and does not follow it.

 - `D` : To correct overshoot problem of `P` controller, using rate of `CTE` is the simple solution. In other word, using how car approaches fast or slowly to desired trajectory. By adding 'D'(derivative) component to error measurement, we can make vehicle avoid overshoot.

 - `I` : When car's alignment is not right, certain amount of steering is needed to compensate mis-alignment. In that situation, steering angle 0 can't minimize `CTE` or can't follow the reference line indefinitely. To avoid that situation, `I`(integral) component which is accumulation of `CTE` over time is used for updating error measurement. 'I' indicate if the vehicle spending more time on one side of the trajectory or the other.

### Final hyperparameters

My final hyperparameters are chosen by manually. Of course, Twiddle or other optimization methods finds much better PID parameters, But manual parameter setting is enough for this project. 

At first, I started with parameters from lectures, `(P, D, I) = (0.2, 3.0, 0.004)`. There is big oscillation and It makes car off the track, So I increased D to `8`. Also I realized there is no bias in the simulator by adjusting `I`, so I decided `I` parameter to `0`.

My final parameters are `(P, I, D) = (0.2, 0, 8.0)`.

## Result

### YouTube link
The video shows that the vehicle successfully drove two laps around the track.
[![PID Controller result](https://img.youtube.com/vi/ID3rG3FRnVM/0.jpg)](https://www.youtube.com/watch?v=ID3rG3FRnVM)

## Reference
 - [Controlling Self Driving Cars](https://youtu.be/4Y7zG48uHRo)

