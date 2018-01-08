# **Project: PID Controller**
[![Udacity - Self-Driving Car Engineer NanoDegree Program](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)


## Overview
This repository contains all the codes and reflection that required for completing project.

Build instruction and dependency of this project is identical to [upstream repository](https://github.com/udacity/CarND-PID-Control-Project) which is the starter code repository of udacity.


## Reflection

### The effect each of the P, I, D components

 - `P` : `P` stands for `proportional`. It makes car overshoot and oscillate to center line. The larger `P` makes car the faster oscillation. 

 - `D` : `D` means `differential`. `D` compensates overshoot from `P` by counter steering. The larger `D` makes car approaches slowly to center line. 

 - `I` : When car's alignment is not right, certain amount of steering is needed to compensate mis-alignment. `I` compensates bias in the system. The larger `I` makes car oscillate faster.

### Final hyperparameters

My final hyperparameters are chosen by manually. Of course, Twiddle or other optimization methods finds much better PID parameters, But manual parameter setting is enough for this project. 

At first, I started with parameters from lectures, `(P, D, I) = (0.2, 3.0, 0.004)`. There is big oscillation and It makes car off the track, So I increased D to `8`. Also I realized there is no bias in the simulator by adjusting `I`, so I decided `I` parameter to `0`.

My final parameters are `(P, I, D) = (0.2, 0, 8.0)`.

## Result

### YouTube link
The video shows that the vehicle successfully drove two laps around the track.
[![PID Controller result](https://img.youtube.com/vi/ID3rG3FRnVM/0.jpg)](https://www.youtube.com/watch?v=ID3rG3FRnVM)


