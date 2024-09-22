# Project-Map_rover
---

# Map Rover - R-SMART Algorithm Implementation

This project implements the **R-SMART (Reinforcement Learning with Stochasticity in Actions and Rewards)** algorithm for navigating a map. The agent (rover) learns an optimal policy for traversing the map using reinforcement learning principles.

## Table of Contents

- [Overview](#overview)
- [Algorithm](#algorithm)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Overview

The **Map Rover** project is an example of using reinforcement learning (RL) for navigating a grid-based environment (map). The rover moves across cells in the map, with rewards and penalties guiding its learning process. The project demonstrates the **R-SMART algorithm** in a grid world, where each cell represents a state, and the rover can perform actions to move between cells.

In this project, the goal of the rover is to reach a target location, receiving rewards for success and penalties for failure.

## Algorithm

The **R-SMART** algorithm is a variant of the traditional Q-Learning algorithm but introduces:
- **Stochasticity** in both actions and rewards, making the environment non-deterministic.
- **Learning rate** and **discount factor** to balance immediate vs. long-term rewards.

Key concepts:
- **State Space**: The grid on which the rover moves.
- **Action Space**: The set of possible actions (Up, Down, Left, Right).
- **Rewards**: A reward signal that encourages or discourages the rover's movements.
- **Q-Values**: A table of learned values for each state-action pair.

The rover updates its knowledge of the environment using the **R-SMART update rule**:

Q(s, a) ← (1 - α) * Q(s, a) + α * (r + γ * max_{a'} Q(s', a'))

Where:


- `α` is the learning rate
- `γ` is the discount factor
- `r` is the immediate reward
- `s` and `s'` are the current and next states


## Features

- **Grid-Based Map**: A customizable grid that represents the rover's environment.
- **Stochastic Rewards**: Randomness in the reward system for added complexity.
- **Dynamic Learning**: The rover learns over time by exploring different paths.
- **Visualization**: The state space and Q-value updates can be visualized for analysis.

## Installation

To set up the project on your local machine:

1. Clone the repository:
    ```bash
    git clone https://github.com/username/map-rover-rsmart.git
    ```

2. Navigate into the project directory:
    ```bash
    cd map-rover-rsmart
    ```

3. Install required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. Run the `map_rover.py` script to start training the rover on a predefined grid:
    ```bash
    python map_rover.py
    ```

2. Customize the grid and rover's starting point in the configuration section of the script.

3. Visualize the results after training by running:
    ```bash
    python visualize_results.py
    ```

### Configuration

- **Grid Size**: The grid size can be modified in the `map_rover.py` file.
- **Rewards and Penalties**: Customize the rewards for reaching certain states (e.g., the target) and penalties for undesirable moves.

## Results

The rover will learn to efficiently navigate the grid world after a number of training episodes. The learned Q-values will guide the rover to the optimal path based on accumulated rewards.

You can expect:
- **Exploration**: The rover initially explores the map randomly.
- **Exploitation**: Over time, the rover learns to exploit the best paths based on its Q-value updates.

An example of the final Q-value table is shown below:

| State | Up   | Down | Left | Right |
|-------|------|------|------|-------|
| 0,0   | 0.5  | 0.2  | -0.1 | 0.7   |
| 0,1   | 0.4  | 0.3  | 0.2  | 0.6   |
| ...   | ...  | ...  | ...  | ...   |

## Contributing

Contributions are welcome! Feel free to submit issues, fork the repository, and create pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
