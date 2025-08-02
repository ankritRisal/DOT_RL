
# 🚚 Smart Logistic Transportation using Reinforcement Learning

A multi-agent reinforcement learning (MARL) project designed to optimize pickup and delivery tasks in a grid-based logistics environment. This project leverages Q-learning to train independent agents to navigate, avoid obstacles, and efficiently deliver items in a simulated 10x10 warehouse grid.

---

## 📌 Table of Contents

- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Algorithms Used](#algorithms-used)
- [Results](#results)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [Limitations](#limitations)
- [Future Enhancements](#future-enhancements)
- [Team](#team)
- [License](#license)

---

## 🧠 Project Overview

In this project, we simulate a smart logistic warehouse system where 3 autonomous agents independently pick up and deliver 3 objects to their respective goals in a 10x10 grid world with static obstacles. The agents are trained using the Q-learning algorithm to develop optimal delivery policies through trial and error over 10,000 episodes.

This system highlights the potential of reinforcement learning in real-world logistic automation by minimizing delivery time and avoiding collisions.

---

## ✨ Key Features

- Multi-agent environment with 3 agents, 3 objects, and 3 goals
- Independent Q-learning (no centralized controller)
- 10x10 grid environment with obstacles
- Separate Q-tables for pickup and delivery phases
- Visualization of environment state and agent movements
- Modular and extendable simulation code

---

## 🧰 Architecture

- **Environment**: 10x10 grid world with positions for agents, objects, goals, and obstacles
- **Agent Design**:
  - Moves in 4 directions: up, down, left, right
  - Learns through rewards (+0 for success, -1 otherwise)
- **State Space**: (x, y) location of the agent in the grid
- **Action Space**: ['UP', 'DOWN', 'LEFT', 'RIGHT']
- **Reward System**:
  - Penalizes every time step (-1)
  - Zero reward on successful delivery

---

## 📚 Algorithms Used

### Q-Learning
A value-based reinforcement learning algorithm is used for each agent independently.

#### Q-Update Rule:
\[
Q(s, a) \leftarrow Q(s, a) + \alpha [R + \gamma \max_a Q(s', a') - Q(s, a)]
\]

- \(\alpha\) (alpha): Learning rate  
- \(\gamma\) (gamma): Discount factor  
- \(\epsilon\)-greedy: Exploration strategy

---

## 📊 Results

- Agents successfully learned optimal pickup and delivery policies.
- Converged within 10,000 episodes.
- Trained agents avoided obstacles and minimized delivery time.
- Visualization plots show significant improvement after training.

---

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.8+
- Jupyter Notebook / VS Code / Any Python IDE

### Libraries
```bash
pip install numpy matplotlib
```

### Running the Code
```bash
jupyter notebook gridX10_Testing.ipynb
```

---

## 🕹️ Usage

1. Modify grid environment and initialize agent, object, and goal locations in `gridX10_Testing.ipynb`.
2. Run the Q-learning training cell.
3. Visualize agent navigation before and after training.

---

## 🚧 Limitations

- Does not generalize to dynamic or unseen environments (no neural networks).
- Object and goal positions are static.
- Requires retraining for any change in configuration.

---

## 🚀 Future Enhancements

- Use deep Q-networks (DQN) for better generalization.
- Add dynamic goals/objects and randomized environments.
- Introduce cooperative strategies between agents.
- Real-world robotic simulation integration.

---

## 👨‍💻 Team

| Name           | Role           |
|----------------|----------------|
| Aayush Basnet  | Developer      |
| Ankrit Risal   | Developer      |
| Bhuwan Dhakal  | Developer      |
| Supervisor     | Dr. Dibakar Raj Panta, Associate Professor |

---

## 📄 License

This project is for academic and educational purposes. For usage and publication rights, contact the [Department of Electronics and Computer Engineering, ACEM].
