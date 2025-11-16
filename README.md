# Campus Navigation Project

This project implements a 5×5 campus navigation environment where an agent must move from the Hostel (Start) to the Library (Goal) while avoiding obstacles. Four reinforcement learning algorithms are used to learn optimal paths:

* Q-Learning
* SARSA
* Monte Carlo Control
* Temporal Difference (TD-λ)

All implementations are contained in a single file:

**`new_project.py`**

## 1. Project Overview

The environment is a grid-world representing a campus layout.
Each cell represents a location such as:

* Hostel
* Walkways
* Admin Buildings (obstacles)
* Park (obstacle)
* Sports Complex (obstacle)
* Library (goal)

The agent receives rewards based on movement, obstacles, and reaching the goal.
This project demonstrates how different RL algorithms learn navigation policies under the same environment.

# 2. Features

* Custom 5×5 campus environment
* Four RL algorithms implemented from scratch
* Visualized grid with building names
* Arrow-based path visualization
* Reward graphs for each algorithm
* Q-Table outputs for Q-Learning and SARSA
* Complete comparison between methods
  
# 3. File Structure

```
new_project.py
```

This file contains:

1. Environment code (grid, labels, colors, movement)
2. Q-Learning implementation
3. SARSA implementation
4. Monte Carlo Control implementation
5. Temporal Difference (TD-λ) implementation
6. Visualization utilities

# 4. How to Run

Step 1: Install dependencies
```
pip install numpy matplotlib
```
Step 2: Execute the project
```
python new_project.py
```
When executed, the file will:
* Train each RL algorithm
* Display reward graphs
* Plot optimal navigation paths
* Print Q-Tables and total costs
* Show the complete campus grid

# 5. Campus Environment

The agent interacts with the environment as follows:

| Location Type                   | Reward  |
| ------------------------------- | ------- |
| Walkway                         | -1      |
| Obstacles (Admin, Park, Sports) | -5      |
| Goal (Library)                  | +10     |
| Invalid Move                    | Penalty |

The grid includes full labels for each cell and is displayed visually.

# 6. Algorithms Implemented

6.1 Q-Learning
An off-policy TD control method that selects actions greedily.
Update rule:
```
Q[s][a] = Q[s][a] + α * (r + γ * max(Q[s’]) - Q[s][a])
```
Output includes:
* Q-Table
* Total cost
* Optimal path
* Reward vs episode graph
  
# 6.2 SARSA
An on-policy TD control method that follows the same policy it learns.
Update rule:
```
Q[s][a] = Q[s][a] + α * (r + γ * Q[s’][a’] - Q[s][a])
```
Output includes:
* Q-Table
* Total cost
* Optimal path
* Reward graph
* 
# 6.3 Monte Carlo Control
Learns using complete episodes.
Uses return-based updates without bootstrapping.

Outputs:
* Optimal path
* Total cost
* Reward graph
  
# 6.4 Temporal Difference (TD-λ)
Combines TD learning with eligibility traces for more efficient learning.

Outputs:
* Optimal path
* Total cost
* Reward graph
  
# 7. Output Visualizations
The project automatically generates:

1. Reward curves for all algorithms
2. Grid-based path visualizations
3. Arrow-based movement paths
4. Q-Tables (for Q-Learning and SARSA)
5. Final optimal policy results

# 8. Use Cases
This project is useful for:

* Understanding RL fundamentals
* Comparing different RL control methods
* University or research projects
* Demonstrating pathfinding using RL
* Studying convergence and performance differences

#9. Requirements
* Python 3.8 or higher
* numpy
* matplotlib

