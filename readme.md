# Overcooked AI: Cooperative Multi-Agent Reinforcement Learning


Each layout has its own Jupyter notebook. Will require installation of Overcooked AI (see notebook for detail)

!pip install git+https://github.com/HumanCompatibleAI/overcooked_ai.git

![Description](/figure/overcooked_ai.gif)


## Project Overview

This project explores the application of Value Decomposition Networks (VDN) within a dual-agent environment in the Overcooked simulation, modeled after a popular game. The goal is to enhance cooperative strategies between agents to optimize soup delivery across five distinct kitchen layouts.

## Table of Contents

- [Introduction](#introduction)
- [Methodology](#methodology)
- [Results](#results)
- [Metrics](#metrics)
- [Future Work](#future-work)
- [Contributors](#contributors)
- [References](#references)

## Introduction

Overcooked is a simulated environment where two agents collaborate to prepare and deliver onion soups in a restaurant kitchen. This project aims to develop a robust multi-agent system capable of maximizing soup deliveries within a limited number of timesteps by utilizing VDN, which equips each agent with its own Q-network for structured learning and decision-making.

## Methodology

The project employs Value-Decomposition Networks (VDN), which decompose the joint action-value function into the sum of individual action-values for each agent, simplifying the multi-agent learning process. The methodology incorporates advanced techniques such as reward shaping, mirrored experiences, and soft update Q-target networks.

### Key Techniques

- **Input Layer**: Stacked state representation to capture temporal dependencies.
- **Hidden Layers**: Dense layers to learn complex patterns.
- **Output Layer**: Vector of action values for each possible action.
- **Reward Shaping**: Smaller rewards for intermediate tasks to guide agents towards the main goal.
- **Mirrored Experience**: Sharing experiences between agents to improve learning speed and consistency.
- **Soft Update**: Gradual update of Q-target networks to enhance stability.

## Results

The VDN model effectively solved the challenges in the first three kitchen layouts, showing significant improvements in the number of soups delivered. However, the more complex fourth and fifth layouts highlighted the need for further enhancements in the learning models (It will take 12 hours before first soup is made).

### Detailed Results

#### Layout 1

- Training episodes: 1000
- Convergence: Around 300 episodes
- Result: Consistently delivered 11 soups per episode.

#### Layout 2

- Training episodes: 1000
- Convergence: Around 350 episodes
- Result: Consistently delivered 7 soups per episode.

#### Layout 3

- Training episodes: 1500
- Convergence: Around 1400 episodes
- Result: Increasing performance, nearly converged.

#### Layout 4 & 5

- Training episodes: 3000+
- Convergence: Not achieved
- Result: Requires further exploration and learning.

## Metrics

Two primary metrics were used to evaluate the agents' performance:

1. **Number of Onions Put in Pot**: Indicator of task completion towards soup preparation.
2. **Number of Dishes Picked Up**: Reflects agents' progress in delivering soup.

These metrics helped in refining the reward shaping strategy and improving the overall model performance.

## Future Work

Future improvements could include:

- **State Stacking**: Enhancing temporal awareness by stacking multiple consecutive observations.
- **Epsilon Decay Adjustment**: Slower decay rates for more complex layouts to ensure adequate exploration.
- **Integration of New Techniques**: Exploring other multi-agent reinforcement learning strategies to handle higher collaboration requirements.

## Contributors

- Trung Pham ([trungpham89@gmail.com](mailto:trungpham89@gmail.com))

## References

1. Value-Decomposition Networks for Cooperative Multi-agent learning, Peter Sunehag et al., June 2017.
2. Multi-Agent Reinforcement Learning: Foundations and Modern Approaches, Stefano Albrecht, Filippos Christianos, Lukas Schafer, MIT Press, 2024.
