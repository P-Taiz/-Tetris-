# Deep Q-Learning Tetris

This project implements Deep Q-Learning (DQN) to autonomously play the classic game of Tetris. Using reinforcement learning, the system trains a neural network to maximize the score by clearing as many rows as possible while minimizing empty spaces and irregularities in the board.


## Project Overview

Tetris is a well-known puzzle game where players manipulate falling blocks (tetrominoes) to form complete rows, which are then cleared. The goal of this project is to use reinforcement learning techniques to create an AI agent that can learn to play Tetris effectively.

### Key Components
1. **Tetris Environment**: 
    - Simulates the game mechanics, such as generating tetrominoes, detecting collisions, clearing lines, and calculating scores.
2. **Deep Q-Network (DQN)**: 
    - A simple neural network that estimates the best possible action for any given state of the board.
3. **Training and Testing**: 
    - Scripts to train the AI agent and test its performance by letting it play games autonomously.
4. **Visualization**:
    - OpenCV is used to render the game's progress and save gameplay as videos for analysis.


## How It Works

### 1. Environment:

- The game environment (src/tetris.py) defines the rules of Tetris, including block placement, rotations, collision detection, and scoring.
- It also calculates important state features like the number of holes, bumpiness, and column heights.

### 2. Deep Q-Network:

- The neural network (src/deep_q_network.py) predicts Q-values (expected rewards) for all possible actions given the current state of the board.
- It consists of three fully connected layers and uses ReLU activation functions.

### 3. Training:

- During training (train.py), the agent interacts with the Tetris environment and learns by optimizing the Q-values using data from replay memory.
- An epsilon-greedy strategy ensures a balance between exploration (trying new moves) and exploitation (using known good moves).

### 4. Testing:

- Once trained, the model can autonomously play Tetris (test.py) by selecting the best actions based on the learned Q-values.
- The gameplay is rendered in real-time and recorded as a video.


## Running the Project
### Training
- To train the DQN agent, run:
* **python train.py*

### Testing
- After training, use the following command to test the model and record gameplay:
* **python test.py*
- You could find my trained model at trained_models/tetris


## Requirements
* **python 3.10**
* **PIL**
* **cv2**
* **pytorch** 
* **numpy**
* **matplotlib**
* **tensorBoardX**
