# rl-agent-comparison-sarsa-double-q-learning

Defining and Solving a Reinforcement Learning Task

🔍 Project Overview
This project focuses on the implementation and analysis of reinforcement learning (RL) algorithms within a custom grid-world environment. It follows the Gymnasium framework to define a Markov Decision Process (MDP) and then applies classic reinforcement learning methods, SARSA and n-step Double Q-learning, to train an agent to solve the environment. The project emphasizes core RL concepts like state representation, reward mechanisms, and policy evaluation.

🎯 Motivation & Goals
The primary goal of this project is to gain hands-on experience with reinforcement learning theory and implementation. Specifically, the objectives were to:

Design a grid-world environment based on the Gymnasium framework.

Clearly define the states, actions, rewards, and terminal conditions of the environment.

Implement and compare the SARSA and n-step Double Q-learning algorithms.

Analyze and visualize the performance of each algorithm, focusing on cumulative rewards over time.

Demonstrate an understanding of on-policy vs. off-policy learning and the concept of overestimation bias in Q-learning.

🗂 Table of Contents
Installation

Usage

Project Structure

Environment Design

Methodology

Results & Evaluation

Visualizations

Tech Stack

Future Work

Contact

🔧 Installation
Clone the repository and install the necessary Python packages.

git clone <your_repository_url>
cd <your_project_directory>
pip install -r requirements.txt

🚀 Usage
To run the analysis and see the results, simply open the Jupyter Notebook.

jupyter notebook RL_Agent_Comparision.ipynb

The notebook contains all the code for the environment definition, algorithm implementation, training, and visualization.

📁 Project Structure
.
├── RL_Agent_Comparision.ipynb   # Main Jupyter Notebook
├── environment_visualization.ipynb # Bonus visualization notebook
├── warehouse_agent_env.ipynb     # Bonus notebook with a different environment
└── README.md                                    # This file

📊 Environment Design
The core of this project is the LawnMowerEnv class, a custom grid-world environment adhering to Gymnasium standards.

Grid: A 4
times5 grid, resulting in 20 discrete states represented by (x, y) tuples.

Actions: Four discrete actions for movement: Up (0), Right (1), Down (2), and Left (3). Movement is restricted at boundaries.

Rewards:

Goal State (3, 4): A reward of +20 and terminates the episode.

Batteries (3, 0): A positive reward of +10 to encourage the agent to visit these beneficial states.

Rocks (1, 1) and (2, 2): Negative rewards of -20 and -25, respectively, to penalize the agent for entering these states.

Default States: A penalty of -1 per step to encourage finding the shortest path.

⚙️ Methodology
Reinforcement Learning Algorithms
The project implements two distinct tabular reinforcement learning algorithms for comparison:

SARSA (State-Action-Reward-State-Action): An on-policy algorithm that learns the value of the action taken by the current policy. Its update rule depends on the next state-action pair chosen by the same policy.

n-step Double Q-learning: An off-policy algorithm designed to mitigate the overestimation bias inherent in classic Q-learning. It uses two separate Q-tables, Q1 and Q2, to select and evaluate actions, leading to more stable and accurate policies.

Training & Evaluation
Training: Both agents are trained over multiple episodes to learn an optimal policy for navigating the grid.

Policy Evaluation: The greedy policy derived from the learned Q-tables is evaluated by running it for 10 episodes and tracking the total rewards. This provides a direct comparison of the effectiveness of the policies learned by SARSA and n-step Double Q-learning.

🏆 Results & Evaluation
The training outcomes highlighted key differences between the two algorithms:

SARSA: The cumulative rewards for the SARSA agent exhibited greater fluctuations, which is expected due to its on-policy nature. The agent learned a policy that successfully navigates to the goal, but its path may not be the absolute shortest because it is learning from its own exploratory actions.

n-step Double Q-learning: The cumulative rewards for the n-step Double Q-learning agent stabilized at a higher level over time. This demonstrates its success in reducing overestimation bias, leading to a more optimal and consistent policy, as evidenced by the provided plots.

📸 Visualizations
The following plot compares the total rewards obtained per episode for both the SARSA and Double Q-learning agents during training, demonstrating the superior stability and performance of the Double Q-learning approach.

🛠 Tech Stack
Languages & Tools: Python 3.x, Jupyter Notebook, Gymnasium

Data Handling: NumPy

Visualization: Matplotlib

Algorithms: SARSA, n-step Double Q-learning

🌱 Future Work
Integrate a deep reinforcement learning model (e.g., DQN) to handle larger or more complex environments.

Implement a full visualization of the agent's path on the grid for each episode to better understand its learned behavior.

Introduce stochastic elements (e.g., random movement) to the environment to test algorithm robustness in uncertain conditions.

📬 Contact
Vinay Trinadh Naraharisetty
📧 vinaytrinadh9910@gmail.com
🔗 LinkedIn
🔗 GitHub

Feel free to reach out for questions, feedback, or collaboration!