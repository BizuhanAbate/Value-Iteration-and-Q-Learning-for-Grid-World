# Value Iteration and Q-Learning for Grid World

## Overview
This repository contains implementations of Value Iteration and Q-Learning algorithms to solve a 5x5 Grid World environment. 
The environment consists of an agent that moves in four directions (Up, Down, Left, Right) with rewards assigned for each step and for reaching the goal state. 
The objective is to find the optimal policy using Value Iteration and train the agent using Q-Learning.

## Environment Description
- The Grid World is a 5x5 grid.
- The agent can move in four directions: Up, Down, Left, and Right.
- Each step incurs a reward of -1, and reaching the goal state gives a reward of +10.
- The goal state is (4,4).
- The agent must learn the optimal path to maximize cumulative rewards.

## Implementation

### 1. Value Iteration
Value Iteration is a Dynamic Programming technique used to compute the optimal value function and derive an optimal policy for an MDP.

#### Parameters:
- Discount factor (Gamma): `0.9`
- Convergence threshold: `1e-4`
- Reward structure:
  - `-1` for every move
  - `+10` for reaching the goal

#### Steps:
1. Initialize the Value Function (V) to zero.
2. Iterate until the value function converges:
   - For each state, update its value using the Bellman equation.
   - Choose the best action maximizing expected future rewards.
3. Extract the optimal policy from the final value function.

#### Output:
- The optimal policy is printed using symbols:
  - `^` (Up), `v` (Down), `<` (Left), `>` (Right)
  - `G` represents the Goal state.

### 2. Q-Learning
Q-Learning is a model-free reinforcement learning algorithm used to learn the optimal action-value function through exploration and exploitation.

#### Parameters:
- Learning rate (Alpha): `0.5`
- Discount factor (Gamma): `0.9`
- Episodes: `500`
- Reward structure:
  - `-1` for every move
  - `+10` for reaching the goal

#### Steps:
1. Initialize the Q-table with zeros.
2. For each episode:
   - Start at the initial state `(0,0)`.
   - Choose an action randomly and move to the next state.
   - Update the Q-value using the Q-learning update rule:
     
     ![Q learnng update rule](https://github.com/user-attachments/assets/c5515a29-69f9-441a-8608-6d0d98839366)

   
   - Repeat until the goal state is reached.
3. Print the learned Q-values after training.

## Running the Code
To run the implementations, execute the Python script:
```bash
python Value Iteration Gridworld Algorithm.py
python Basic Q-learning Gridworld  Algorithm.py
```

## Expected Output
- The optimal policy computed via Value Iteration.
- The Q-values learned through Q-Learning.

## Dependencies
Ensure you have the following installed:
- Python 3
- NumPy

You can install NumPy using:
```bash
pip install numpy
```

## Conclusion
This project demonstrates how Value Iteration and Q-Learning solve an MDP in a Grid World environment. 
Value Iteration provides an optimal policy using dynamic programming, while Q-Learning enables an agent to learn the best actions through reinforcement learning.

