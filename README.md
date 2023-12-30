# Deep Q-Network Agent for Pong Game

## Overview

This script implements a reinforcement learning agent using a Deep Q-Network (DQN) to play the classic game of Pong. The agent operates in an environment provided by the game, receiving pixel data as input and learning to predict the optimal action (move up, move down, or stay) to maximize its score against an opponent. The script employs concepts such as Q-Learning, experience replay, and epsilon-greedy strategy for exploration and exploitation.

## Components

### Environment
- **Pong Game**: A simple version of the Pong game where two paddles can move vertically to hit a ball back and forth.
- **Pygame**: Used for rendering the game and providing a graphical interface.

### DQN Agent
- **Neural Network Architecture**: Consists of convolutional neural layers and fully connected layers to process the pixel input into action values.
- **Epsilon-Greedy Strategy**: Balances exploration of new actions with exploitation of known good actions.
- **Experience Replay**: Remembers past experiences and learns from randomly sampled previous states, providing efficiency and stability to the learning process.
- **Action Set**: The agent can choose to move the paddle up, down, or stay in place.

## How it Works

1. **Initialize**: Set up the Pong environment and the DQN agent with a randomly initialized neural network.
2. **Frame Processing**: Process the game frame into a suitable format for the neural network (grayscale, resized, and stacked).
3. **Action Selection**: Use the epsilon-greedy strategy to select an action from the set of possible actions.
4. **Learning from Experience**: Store the state, action, reward, and next state into a replay memory. Sample from this memory to train the network.
5. **Training**: Use backpropagation to update the network weights based on the loss between the predicted Q-values and the target Q-values.

## Usage

Before running the script, ensure the required libraries (`pygame`, `tensorflow`, `numpy`, `cv2`) are installed. Adjust hyperparameters such as ACTIONS, GAMMA, INITIAL_EPSILON, FINAL_EPSILON, OBSERVE, REPLAY_MEMORY, and BATCH as needed.

Run the script to train the agent. The agent's performance (action, reward, Q-value) will print to the console, and the game will render if `render` is set to `True`. The script saves the model's state after a specified number of timesteps.

## Hyperparameters

- **ACTIONS**: Number of valid actions (3 for Pong: up, down, stay).
- **GAMMA**: Discount factor for future rewards.
- **INITIAL_EPSILON & FINAL_EPSILON**: Parameters to control the exploration rate.
- **EXPLORE & OBSERVE**: Timesteps over which to anneal epsilon and observe the performance before training starts.
- **REPLAY_MEMORY**: The size of the memory buffer for experience replay.
- **BATCH**: Batch size for training from replay memory.

## Conclusion

This DQN agent demonstrates a foundational approach in reinforcement learning, applying a neural network to learn policies directly from high-dimensional sensory inputs. As it trains, the agent improves its strategy for playing Pong, learning to balance the short-term and long-term rewards effectively.

