## Mobile Manipulation: Papers
Mobile Manipulation (**MM**) lies at the intersection of mobile robots (e.g., wheeled, legged, and aerial robots) and manipulation (e.g., dual arm, single arm, etc.). However, robotic researchers predominantly concentrate on wheeled or legged robots equipped with a single arm, primarily due to the control complexity associated with aerial robots and dual-arm systems.

The primary challenge in **MM** is to coordinate the mobility and manipulation to address long-horizon and generalized tasks, which are inherently more challenging than stationary manipulation. Specifically, the objective is to enable robots to navigate within a clustered environment while concurrently interacting with the surroundings using their manipulator. Currently, the overall strategies to achieve this can be categorized into **Hierarchical** (i.e., addressing the base and manipulator separately) and **Whole-body** (i.e., addressing the base and manipulator simultaneously) motion planning and control. Both approaches encounter distinct challenges, as well as some shared obstacles that need to be addressed.

Challenges include:
1. Understanding the unstructured environment;
2. Obstacle avoidance and self-collision avoidance;
3. Ensuring graspability for the target object;
4. Hands-off errors within the skill chaining in a long-horizon task (Hierarchical);
5. Skill coordination in a complex task requiring multiple skills simultaneously (Hierarchical);
6. High controlling complexity due to a high degree of freedom (Whole-body);
7. ...

Regardless of the chosen strategy, there are various methods to implement it: **Classical** methods (e.g., model predictive control), **Learning-Based** methods (e.g., reinforcement learning, imitation learning, large language models), and **Learning + Classical** methods. **Learning-Based** methods, in particular, stand out due to their generality and efficiency in tackling complex tasks that are challenging to model accurately. Consequently, the focus here will primarily be on learning-based methods. Additionally, to encourage the development of the **MM** community, researchers have proposed some **Benchmarks** and **Challenges** that offer convenient platforms for the development of custom algorithms and standard metrics for evaluation.

In this repository, I summarize all the aforementioned strategies, methods, benchmarks, and challenges, along with the papers I have read. For some papers related to **Learning-Based MM**, I will provide brief introductions to their core ideas, and methodologies. Links to these papers and codes (if open-sourced) are also included. The table of contents is outlined below.

- [Mobile Manipulation: Papers](#mobile-manipulation-papers)
- [0. Review](#0-review)
- [1. Benchmarks \& Challenges](#1-benchmarks--challenges)
- [2. Classical](#2-classical)
- [3. Reinforcement Learning (RL)](#3-reinforcement-learning-rl)
  - [3.1 Hierarchical RL](#31-hierarchical-rl)
  - [3.2 Whole-body RL](#32-whole-body-rl)
  - [3.3 RL+Priors](#33-rlpriors)
  - [3.4 RL-Training](#34-rl-training)
- [4. Imitation Learning](#4-imitation-learning)
- [5. Large Language Models (LM)](#5-large-language-models-lm)


## 0. Review

**[Machines 2022]** Motion Planning for Mobile Manipulators—A Systematic Review, [[paper](https://www.mdpi.com/2075-1702/10/2/97)] [[code](https://github.com/sandakalum/Mobile-Manipulator-Planning.git)]

## 1. Benchmarks & Challenges

**[CVPR 2021]** ManipulaTHOR: A Framework for Visual Object Manipulation, [[paper](http://arxiv.org/abs/2104.11213)] [[code](https://github.com/allenai/manipulathor/)] [[website](https://prior.allenai.org/projects/manipulathor)]

**[NeurIPS, 2021]** Habitat 2.0: Training Home Assistants to Rearrange their Habitat, [[paper](http://arxiv.org/abs/2106.14405)] [[code](https://github.com/facebookresearch/habitat-lab)]

**[arXiv 2022]** ProcTHOR: Large-Scale Embodied AI Using Procedural Generation, [[paper](https://arxiv.org/abs/2206.06994)] [[code](https://colab.research.google.com/drive/1Il6TqmRXOkzYMIEaOU9e4-uTDTIb5Q78)] [[website](https://procthor.allenai.org/#explore)]

**[arXiv 2023]** HomeRobot: Open Vocabulary Mobile Manipulation, [[paper](https://arxiv.org/pdf/2306.11565.pdf)] [[code](https://github.com/facebookresearch/home-robot)] [[website](https://ovmm.github.io/)]

**[arXIv 2023]** Harmonic Mobile Manipulation, [[paper](http://arxiv.org/abs/2312.06639)] [[website](https://rchalyang.github.io/HarmonicMM/)]

**[NeurIPS 2023]** UniTeam: Open Vocabulary Mobile Manipulation Challenge, [[paper](http://arxiv.org/abs/2312.08611)]

**[ICLR 2023]** ManiSkill2: A Unified Benchmark for Generalizable Manipulation Skills, [[paper](http://arxiv.org/abs/2302.04659)] [[code](https://github.com/haosulab/ManiSkill2)] [[website](https://maniskill2.github.io/)]

## 2. Classical

**[ICRA 2013]** Robot placement based on reachability inversion, [[paper](https://ieeexplore.ieee.org/document/6630839)]

**[ICRC 2018]** Reuleaux: Robot Base Placement by Reachability Analysis, [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8329892)] [[code](https://github.com/ros-industrial-consortium/reuleaux)]

**[IROS 2018]** Coupling Mobile Base and End-Effector Motion in Task Space, [[paper](https://ieeexplore.ieee.org/document/8593534)]

**[ICRA 2019]** Whole-Body MPC for a Dynamically Stable Mobile Manipulator, [[paper](http://arxiv.org/abs/1902.10415)]

**[ICRA 2020]** Perceptive Model Predictive Control for Continuous Mobile Manipulation, [[paper](https://ieeexplore.ieee.org/abstract/document/9145591)] [[code](https://github.com/leggedrobotics/perceptive_mpc)]

**[ICRA 2020]** Planning an Efficient and Robust Base Sequence for a Mobile Manipulator Performing Multiple Pick-and-place Tasks, [[paper](https://ieeexplore.ieee.org/document/9196999)]

**[ICRA 2022]** A Collision-Free MPC for Whole-Body Dynamic Locomotion and Manipulation, [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9812280)]

**[ICRA 2022]** Combining Navigation and Manipulation Costs for Time-Efficient Robot Placement in Mobile Manipulation Tasks, [[paper](https://ieeexplore.ieee.org/document/9830863)]

**[RSS 2023]** Demonstrating Mobile Manipulation in the Wild: A Metrics-Driven Approach, [[paper](http://www.roboticsproceedings.org/rss19/p055.pdf)]

## 3. Reinforcement Learning (RL)

### 3.1 Hierarchical RL

**[CoRL 2019]** HRL4IN: Hierarchical Reinforcement Learning for Interactive Navigation with Mobile Manipulators, [[paper](https://arxiv.org/abs/1910.11432)] [[code](https://github.com/ChengshuLi/HRL4IN)] [[website](https://sites.google.com/view/hrl4in)]

- *Leveraged RL in **both high-level policy**—which embodiment (e.g. base or arm or both) to use **and low-level policy**—the corresponding control policy for base or arm.*

**[ICRA 2021]** Learning Kinematic Feasibility for Mobile Manipulation through Deep Reinforcement Learning, [[paper](http://arxiv.org/abs/2101.05325)] [[code](https://github.com/robot-learning-freiburg/kinematic-feasibility-rl)] [[website](https://github.com/robot-learning-freiburg/kinematic-feasibility-rl?tab=readme-ov-file)]

- *First, generated a rough trajectory for the end-effector (possibly infeasible in kinematics), then used RL to the **base policy** to achieve **the arm's kinematic feasibility**.*

**[ICRA 2021]** ReLMoGen: Leveraging Motion Generation in Reinforcement Learning for Mobile Manipulation, [[paper](http://arxiv.org/abs/2008.07792)] [[website](https://svl.stanford.edu/projects/relmogen/)]

- *Similar to HRL4IN, but leveraged **motion generation** for the low-level policy.*

**[arXIv 2022]** Multi-skill Mobile Manipulation for Object Rearrangement, [[paper](http://arxiv.org/abs/2209.02778)] [[code](https://github.com/Jiayuan-Gu/hab-mobile-manipulation)] [[website](https://sites.google.com/view/hab-m3)]

- *Based on Habitat 2.0, replace point-goal navigation skill with **region-goal** navigation skill and stationary manipulation skill with **mobile** manipulation skill (i.e. replace arm action space with arm-base action space)*

**[ICRA 2022]** Robot Learning of Mobile Manipulation with Reachability Behavior Priors, [[paper](http://arxiv.org/abs/2203.04051)] [[code](https://github.com/iROSA-lab/rlmmbp)] [[website](https://pearl-lab.com/2022/02/24/rlmmbp/)]

**[ICRA 2022]** Combining Learning-based Locomotion Policy with Model-based Manipulation for Legged Mobile Manipulators, [[paper](https://ieeexplore.ieee.org/document/9684679)]

- *Leveraged RL to produce **robust locomotion policies** for legged robots with the **prediction of the external wrench** and **zero-shot adapt** for manipulators **unseen** during training.*

**[arXiv 2023]** ASC: Adaptive Skill Coordination for Robotic Mobile Manipulation, [[paper](http://arxiv.org/abs/2304.00410)]

- *Leveraged RL to train **a coordination policy** **that activates the appropriate (pre-trained and frozen) skills**, depending on different **observations**.*

### 3.2 Whole-body RL

**[Sensors 2019]** Learning Mobile Manipulation through Deep Reinforcement Learning, [[paper](https://www.mdpi.com/1424-8220/20/3/939)]

**[arXiv 2020]** Whole-Body Control of a Mobile Manipulator using End-to-End Reinforcement Learning, [[paper](http://arxiv.org/abs/2003.02637)]

**[RSS 2020]** Spatial Action Maps for Mobile Manipulation, [[paper](https://www.roboticsproceedings.org/rss16/p035.pdf)] [[code](https://github.com/jimmyyhwu/spatial-action-maps)] [[website](https://spatial-action-maps.cs.princeton.edu/)]

- *Represented the set of possible **actions by a pixel map—spatial action map**, which **aligned with the input image** of the current state, in order to help policy learn with **dense action representations**.*

**[CoRL 2021]** Fully Autonomous Real-World Reinforcement Learning with Applications to Mobile Manipulation, [[paper](http://arxiv.org/abs/2107.13545)] [[website](https://sites.google.com/view/relmm?pli=1)]

- *Proposed a **curricular training** method with **autonomous reseting in the real world**, so that the navigation and grasping skill can be trained automatically **without human intervention**.*

**[CoRL 2022]** Deep Whole-Body Control: Learning a Unified Policy for Manipulation and Locomotion, [[paper](https://manipulation-locomotion.github.io/resources/Deep-Whole-Body-Control.pdf)] [[code](https://github.com/MarkFzp/Deep-Whole-Body-Control)] [[website](https://manipulation-locomotion.github.io/)]

- *For a legged mobile manipulator, learned a **unified policy for coordinated manipulation and locomotion** and **regularized online adaptation for sim-to-real transfer**.*

**[arXIv 2023]** Harmonic Mobile Manipulation, [[paper](http://arxiv.org/abs/2312.06639)] [[website](https://rchalyang.github.io/HarmonicMM/)]

- *Proposed an end-to-end learning approach that **jointly optimizes navigation and manipulation**, which support more complex tasks*

**[WACV 2023]** Towards Disturbance-Free Visual Mobile Manipulation, [[paper](https://ieeexplore.ieee.org/document/10030790/)] [[code](https://github.com/allenai/disturb-free)] [[website](https://sites.google.com/view/disturb-free)]

- *Based on ManipulaTHOR, to address the disturbance (i.e. a subset of collision, where an object is moved by some distance caused by a collision) problem, **incorporated a disturbance penalty into the reward** function in the RL and **utilized supervised learning to train a disturbance prediction** as an auxiliary task.*

**[ICRA 2023]** Robotic Table Wiping via Reinforcement Learning and Whole-body Trajectory Optimization, [[paper](https://ieeexplore.ieee.org/document/10161283)]

- *Focusing on **Table Wiping** task, described crumbs and spill dynamics with a **stochastic differential equation (SDE)**, solve the **constrained Markov decision process (CMDP) via RL** and optimize the whole trajectory to **avoid self-collisions and obstacles**.*

**[RSS 2023]** Causal Policy Gradient for Whole-Body Mobile Manipulation, [[paper](http://arxiv.org/abs/2305.04866)] [[code](https://github.com/JiahengHu/CausalMoMa)] [[website](https://sites.google.com/view/causal-moma)]

- *Explored the **causality from action space to reward** via RL and thus reduces gradient variance in the policy learning, stabilizing the training process.*

### 3.3 RL+Priors

**[ICRA 2022]** Robot Learning of Mobile Manipulation with Reachability Behavior Priors, [[paper](http://arxiv.org/abs/2203.04051)] [[code](https://github.com/iROSA-lab/rlmmbp)] [[website](https://pearl-lab.com/2022/02/24/rlmmbp/)]

- ***Reachability Priors**.*

**[arXiv 2022]** Mobile Manipulation Leveraging Multiple Views, [[paper](https://www.cs.columbia.edu/~allen/PAPERS/iros_2022_mobile_manip.pdf)]

- ***Visibility Priors**.*

**[arXiv 2023]** Active-Perceptive Motion Generation for Mobile Manipulation, [[paper](https://arxiv.org/abs/2310.00433v1)]

- ***Visibility Priors**.*

**[ICRA 2024]** GAMMA: Graspability-Aware Mobile MAnipulation Policy Learning based on Online Grasping Pose Fusion, [[paper](http://arxiv.org/abs/2309.15459)]

- ***Graspability Priors**.*

### 3.4 RL-Training

**[ICML 2018]** Soft Actor-Critic: Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor, [[paper](http://arxiv.org/abs/2309.15459)] [[code](https://github.com/haarnoja/sac)]

**[NeurIPS 2019]** Better Exploration with Optimistic Actor-Critic, [[paper](http://arxiv.org/abs/1910.12807)] [[code](https://github.com/microsoft/oac-explore)]

**[ICLR 2020]** DD-PPO: Learning Near-Perfect PointGoal Navigators from 2.5 Billion Frames, [[paper](https://arxiv.org/abs/1911.00357)] [[code](https://github.com/facebookresearch/habitat-api)]

**[ICLR 2022]** Boosted Curriculum Reinforcement Learning, [[paper](https://openreview.net/pdf?id=anbBFlX1tJ1)] [[code](https://github.com/psclklnk/boosted_crl)]

## 4. Imitation Learning

**[RSS 2022]** Human-to-Robot Imitation in the Wild, [[paper](https://human2robot.github.io/resources/paper.pdf)] [[website](https://human2robot.github.io/)]

- *Proposed an efficient one-shot robot learning algorithm, which enables a mobile manipulator to **learn from a third person perspective in the wild** for different manipulation tasks.*
- *Designed a novel objective function for policy learning to **align human and robot videos** and **boost sample efficiency**.*

## 5. Large Language Models (LM)

**[arXiv 2022]** Do As I Can, Not As I Say: Grounding Language in Robotic Affordances, [[paper](http://arxiv.org/abs/2204.01691)] [[code](https://github.com/google-research/google-research/tree/master/saycan)] [[website](https://say-can.github.io/)]

**[CVPR Demo]** LSC: Language-guided Skill Coordination for Open-Vocabulary Mobile Pick-and-Place, [[website](https://languageguidedskillcoordination.github.io/)]

- *An extension of ASC, **leveraging LLM to specify goals** while other parts stay the same with ASC.*