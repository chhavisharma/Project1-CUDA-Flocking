## Project 1 - Flocking
**University of Pennsylvania, CIS 565: GPU Programming and Architecture**

* Author: Chhavi Sharma
  - [LinkedIn](https://www.linkedin.com/in/chhavi275/)
* Tested on: Windows 10, Intel Core(R) Core(TM) i7-6700 CPU @ 3.40GHz 16GB, NVIDIA Quadro P1000 4GB (MOORE100B-06)

### Index

- [Introduction](https://github.com/chhavisharma/Project1-CUDA-Flocking/blob/master/README.md#introduction)
- Algorithm
- Part 1: Naive Boid Simulation
- Part 2: Search Optimization using Uniform Grids
  - Scattered Uniform Grid Search
  - Coherent Uniform Grid Search
- Part 3: Performance Analysis


### Introduction

This repository presents a CUDA accelerated implemtation of the [boids algorithm](https://en.wikipedia.org/wiki/Boids), developed by Craig Reynolds in 1986, which simulates the flocking behaviour of animals such as birds or fishes. Boids is an example of emergent behavior; that is, the complexity of Boids arises from the interaction of individual boids adhering to a set of simple rules. 
The rules applied in the simplest Boids algorithm are as follows:
- Separation: steer to avoid crowding local flockmates
- Alignment: steer towards the average heading of local flockmates
- Cohesion: steer to move towards the average position (center of mass) of local flockmates

An example of the resultant movement is shown below:
<p align="center">
  <img width="400" height="300" src="images/GIF_380.6_fps_Boids_SM_7.0_TITANV.gif">
</p>

Three versions of implementations with increasing levles of search optimization are shown: A naive search over all the neighbours, a scattered uniform grid search and a coherent unifrom grid search. 

### Algorithm

The detialed algorithm that governs the movement of every boid at each timestamp is as follows:


