# Snake Reinforcement Learning

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pygame](https://img.shields.io/badge/Pygame-00897B?style=for-the-badge&logo=python&logoColor=white)

Teaching an AI agent to play Snake using Deep Q-Learning (DQN). The agent starts with zero knowledge of the game and learns entirely through trial and error — improving its score over thousands of episodes.

---

## 🧠 Overview

This project implements a **Deep Q-Network (DQN)** agent that learns to play the classic Snake game autonomously. The human-playable version is included to compare human vs. AI performance.

The agent uses:
- A **neural network** to approximate the Q-value function
- **Experience replay** to learn from past moves
- An **epsilon-greedy** strategy to balance exploration and exploitation

---

## 🗂 Project Structure

```
snake-reinforcement-learning/
├── agent.py              # RL agent — trains the model and makes decisions
├── game.py               # Snake game environment (Pygame)
├── model.py              # Deep Q-Network (neural network)
├── helper.py             # Plotting training progress in real-time
└── snake_game_human.py   # Human-playable version of Snake
```

---

## 🛠 Tech Stack

- **Python** — Core language
- **PyTorch** — Neural network and backpropagation
- **Pygame** — Game environment
- **NumPy** — State representation and array operations
- **Matplotlib** — Real-time training score visualisation

---

## ⚙️ How It Works

### State Representation
The agent observes an 11-dimensional state vector at each step:
- Danger straight, left, right
- Current direction (up, down, left, right)
- Food location relative to head (4 directions)

### Reward Structure
| Event | Reward |
|---|---|
| Eat food | +10 |
| Game over (collision) | -10 |
| No event | 0 |

### Training Loop
1. Agent observes current state
2. Chooses action (explore or exploit)
3. Performs action, observes new state and reward
4. Stores experience in replay memory
5. Trains neural network on random batch from memory

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/monimithra18/snake-reinforcement-learning.git
cd snake-reinforcement-learning

# Install dependencies
pip install pygame torch numpy matplotlib

# Train the AI agent
python agent.py

# Play the game yourself
python snake_game_human.py
```

---

## 📈 Training Progress

The agent's score improves significantly over time. Early games result in quick deaths; after 100+ episodes the agent learns to efficiently chase food and avoid walls.

---

## 🔭 Future Improvements

- Implement Double DQN or Dueling DQN for better stability
- Add a convolutional layer to process raw pixel input
- Experiment with different reward shaping strategies
- Deploy as a web app using WebAssembly

---

*Built by [Monish Mithra Kadiyala](https://linkedin.com/in/monishmithra) ·*
