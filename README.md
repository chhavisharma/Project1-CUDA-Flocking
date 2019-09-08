## Project 1 - Flocking
**University of Pennsylvania
CIS 565: GPU Programming and Architecture**

* Author: Chhavi Sharma ([LinkedIn](https://www.linkedin.com/in/chhavi275/))
* Tested on: Windows 10, Intel Core(R) Core(TM) i7-6700 CPU @ 3.40GHz 16GB, 
             NVIDIA Quadro P1000 4GB (MOORE100B-06)

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

    Cohesion - boids move towards the perceived center of mass of their neighbors
    Separation - boids avoid getting to close to their neighbors
    Alignment - boids generally try to move with the same direction and speed as their neighbors

These three rules specify a boid's velocity change in a timestep. At every timestep, a boid thus has to look at each of its neighboring boids and compute the velocity change contribution from each of the three rules. 

An example of the resultant movement is shown below:
<p align="center">
  <img width="400" height="300" src="images/GIF_380.6_fps_Boids_SM_7.0_TITANV.gif">
</p>

Three versions of implementations with increasing levles of search optimization are shown: A naive search over all the neighbours, a scattered uniform grid search and a coherent unifrom grid search. 

### Algorithm

The pseudo code for the detialed algorithm that governs the movement of every boid at each timestamp is as follows:


