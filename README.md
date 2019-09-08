**University of Pennsylvania, CIS 565: GPU Programming and Architecture,
Project 1 - Flocking**

* Author: Chhavi Sharma
  * [LinkedIn](https://www.linkedin.com/in/chhavi275/)
* Tested on: Windows 10, Intel Core(R) Core(TM) i7-6700 CPU @ 3.40GHz 16GB, NVIDIA Quadro P1000 4GB (MOORE100B-06)

### Index

CUDA Introduction - Flocking
============================
- [Introduction](https://github.com/chhavisharma/Project1-CUDA-Flocking/blob/master/README.md#introduction)
- Algorithm
- Part 1: Naive Boid Simulation
- Part 2: Search Optimization using Uniform Grids
  - Scattered Uniform Grid Search
  - Coherent Uniform Grid Search
- Part 3: Performance Analysis


### Introduction

We present a CUDA accelerated implemtation of the [boids algorithm](https://en.wikipedia.org/wiki/Boids), developed by Craig Reynolds in 1986, which simulates the flocking behaviour of animals such as birds or fishes. Boids is an example of emergent behavior; that is, the complexity of Boids arises from the interaction of individual boids adhering to a set of simple rules. 
The rules applied in the simplest Boids algorithm are as follows:
- Separation: steer to avoid crowding local flockmates
- Alignment: steer towards the average heading of local flockmates
- Cohesion: steer to move towards the average position (center of mass) of local flockmates
An example of the resultant movement is shown below:
![Boid Simulation](/images/[380.6 fps] 565 CUDA Intro_ Boids [SM 7.0 TITAN V] 9_7_2019 11_55_58 PM.gif)
We show three versions of implementations with increasing levles of search optimization: A naive search over all the neighbours, a scattered uniform grid search and a coherent unifrom grid search. 

### Algorithm

The detialed algorithm that governs the movement of every boid at each timestamp is as follows:


