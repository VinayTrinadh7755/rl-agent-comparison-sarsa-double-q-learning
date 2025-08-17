# rl-agent-comparison-sarsa-double-q-learning

## 🔍 Project Overview
This project focuses on the implementation and analysis of reinforcement learning (RL) algorithms within a custom grid-world environment. It follows the Gymnasium framework to define a Markov Decision Process (MDP) and then applies classic reinforcement learning methods, SARSA and n-step Double Q-learning, to train an agent to solve the environment. The project emphasizes core RL concepts like state representation, reward mechanisms, and policy evaluation.

## 🎯 Motivation & Goals
The primary goal of this project is to gain hands-on experience with reinforcement learning theory and implementation. Specifically, the objectives were to:

- Design a grid-world environment based on the Gymnasium framework.
- Clearly define the states, actions, rewards, and terminal conditions of the environment.
- Implement and compare the SARSA and n-step Double Q-learning algorithms.
- Analyze and visualize the performance of each algorithm, focusing on cumulative rewards over time.
- Demonstrate an understanding of on-policy vs. off-policy learning and the concept of overestimation bias in Q-learning.

## 🗂 Table of Contents
- Installation
- Usage
- Project Structure
- Environment Design
- Methodology
- Results & Evaluation
- Visualizations
- Tech Stack
- Future Work
- Contact

---

## 🔧 Installation
Clone the repository and install the necessary Python packages.

```bash
git clone <rl-agent-comparison-sarsa-double-q-learning>
cd <rl-agent-comparison-sarsa-double-q-learning>
pip install -r requirements.txt
```

## 🚀 Usage
To run the analysis and see the results, simply open the Jupyter Notebook.

```bash
jupyter notebook RL_Agent_Comparision.ipynb
```

The notebook contains all the code for the environment definition, algorithm implementation, training, and visualization.

## 📁 Project Structure
```
.
├── RL_Agent_Comparision.ipynb      # Main Jupyter Notebook
├── environment_visualization.ipynb # Bonus visualization notebook
├── warehouse_agent_env.ipynb       # Bonus notebook with a different environment
└── README.md                       # This file
```

## 📊 Environment Design
The core of this project is the `LawnMowerEnv` class, a custom grid-world environment adhering to Gymnasium standards.

- **Grid**: A 4x5 grid, resulting in 20 discrete states represented by (x, y) tuples.
- **Actions**: Four discrete actions for movement: Up (0), Right (1), Down (2), and Left (3). Movement is restricted at boundaries.
- **Rewards**:
  - Goal State (3, 4): A reward of +20 and terminates the episode.
  - Batteries (3, 0): A positive reward of +10 to encourage the agent to visit these beneficial states.
  - Rocks (1, 1) and (2, 2): Negative rewards of -20 and -25, respectively.
  - Default States: A penalty of -1 per step to encourage finding the shortest path.

## ⚙️ Methodology
### Reinforcement Learning Algorithms
The project implements two distinct tabular reinforcement learning algorithms for comparison:

- **SARSA (State-Action-Reward-State-Action)**: An on-policy algorithm that learns the value of the action taken by the current policy.
- **n-step Double Q-learning**: An off-policy algorithm designed to mitigate overestimation bias. It uses two separate Q-tables, Q1 and Q2, for more stable evaluations.

### Training & Evaluation
- **Training**: Agents are trained over multiple episodes to learn an optimal policy.
- **Evaluation**: Greedy policies derived from the Q-tables are evaluated across 10 episodes to compare total rewards.

## 🏆 Results & Evaluation
- **SARSA**: Cumulative rewards showed greater fluctuations, reflecting on-policy learning and exploration tradeoffs.
- **n-step Double Q-learning**: More stable and optimal policy due to reduced overestimation bias; outperformed SARSA in final rewards.

## 📸 Visualizations
Total reward plots comparing SARSA and Double Q-learning highlight the superior performance and stability of Double Q-learning.

## 🛠 Tech Stack
- **Languages & Tools**: Python 3.x, Jupyter Notebook, Gymnasium
- **Data Handling**: NumPy
- **Visualization**: Matplotlib
- **Algorithms**: SARSA, n-step Double Q-learning

## 🌱 Future Work
- Introduce deep RL (e.g., DQN) for complex environments.
- Add full agent path visualizations per episode.
- Introduce stochasticity to test algorithm robustness.

## 📬 Contact
**Vinay Trinadh Naraharisetty**  
📧 vinaytrinadh9910@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/VinayTrinadh)  
🔗 [GitHub](https://github.com/VinayTrinadh)  

Feel free to reach out for questions, feedback, or collaboration!
