# Introduction

## What is Robot Learning about?
Learning to make sequential decisions in the physical world.
**sequential:actions in current round effect the next observations**

## Uniqueness of Robot Learning
### learning
- littile data
- loss function??
- optimization??
- autogressive model not work
### sequential & physical world
- unknown & dynamic
- many tasks 
- unclear goal -> inexact reward function
- regular online adaptation
- fast real-time action
- physics doesn't give a second chance
- continuous physical world

## Goal of Robot Learning
**build general-purpose embodied intelligence**
### where are we today?
- non-learning method:
    Boston Dynamics Atlas humanoid planning and control:
    - trajectory optimization
    - MPC

    Offroad autonomy:
    - sampling-based MPC

    high-speed robot hand (Ishikawa Komuro Lab) in 2009

### why still need robot learning?
- data increases the "upper bound" of algarith,computation and hardware
- non-learning method seperately design each module in robotics