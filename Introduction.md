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

- learning method:
    - Sim2Real and Real2Sim2Real
        - Sim2Real: train in simulation, then deploy in real world (1-1 soccer from Deepmind) **or** train in simulation, then deploy in real world with real-time adaptation
        - Real2Sim2Real: use real data to build/augment/improvement a simulator, train DRL in simulation, deploy in the real world (Swift)

    - Imitation learning with demonstrations:
        collect human demonstrations and do imitation learning

    - Model-based RL
        No simulator.Collect data from real -> learn a model -> obtain a policy -> deploy

    - model-free reinforcement learning
        No simulator.Model-free RL in the real world.Interact directly with the real world.

    - Online adaptation


    - Offline RL
        No simulator.Learn from offline data.Doesn't rely on expert data.Can be better than expert.

### why still need robot learning?
- data increases the "upper bound" of algarith,computation and hardware
- non-learning method seperately design each module in robotics:
- robot learning can unify the module below: planning,perception,control
    **traditional method**
    ```mermaid
    graph TD;
        A[Raw sensory input] --> B[explicit state estimation];
        B --> C[Decision making];
        C --> D[raw outputs];

        subgraph computer vison
            A
            B
        end
        subgraph robotics
            C
            D
        end
   ```
- robot learning can also improve each module especially when it's embodied (we have made more progress in this than unifying these modules)  

