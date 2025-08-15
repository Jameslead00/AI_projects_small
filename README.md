# AI_projects_small
This repo holds Jupyter notebooks and relevant files for a few small AI projects completed by me.

# AI Fairness Case Study Notebook
This notebook demonstrates a full workflow for building, evaluating, and auditing a predictive model for fairness using US Census employment data. The project is designed for transparency and reproducibility, and covers the following tasks:

## Structure
1. Data Preparation

- Downloaded ACS employment data via folktables.
- Filtered for working-age adults (25–65) and selected Black and White racial groups.
  
2. Model Training
- Built a logistic regression pipeline with feature scaling.
- Split data into training and test sets, trained the model, and exported raw data for reproducibility.

3. Model Performance & Calibration
- Evaluated accuracy and generated a calibration plot with confidence intervals.
- Binned predicted probabilities and compared observed reemployment rates to assess model reliability.

4. Group-wise Analysis
- Compared score distributions and performance metrics (accuracy, precision, recall, F1) for Black and White job seekers.
- Assessed calibration for each group and performed statistical tests for differences in reemployment rates per score bin.
- Calculated fairness metrics (base rate, positive rate, TPR, FNR, FPR, TNR) and tested for significant group differences.

5. Decision-Maker Utility & Threshold Optimization
- Defined a utility matrix representing costs for different decisions (coaching vs. no coaching).
- Searched for the optimal decision threshold to maximize agency utility, compared it to the default threshold, and quantified improvement.

6. Fairness Criterion (Moral Analysis)
- Checked for fairness by comparing the fraction of individuals in each group who received coaching and found employment.
- Used a two-proportion z-test to assess statistical significance of group differences.

7. Trade-off Analysis & FairnessLab Export
- Explored the trade-off between maximizing utility and satisfying fairness constraints.
- Exported results (scores, decisions, sensitive attribute, ground truth) to CSV for further analysis in FairnessLab.

8. Deployment Evaluation
- Applied the trained model to data from four years later to simulate real-world deployment.
- Re-evaluated performance, calibration, group metrics, and fairness criteria on new data.
- Exported deployment results for reproducibility and external fairness analysis.

___

# Deep Q-Learning for Moon Landing
This project implements a Deep Q-Network (DQN) agent to solve the LunarLander-v2 environment from Gymnasium. The agent learns to control a lunar lander and safely land it on the moon using reinforcement learning techniques.

1. Introduction & Objective
- Explained the goal: train a DQN agent to land a spaceship in the LunarLander-v2 environment.

2. Environment Setup
- Described the LunarLander-v2 environment, observation and action spaces, and reward structure.
- Installed required dependencies: gymnasium[box2d], stable-baselines3, and system libraries for video rendering.
- Set up a virtual display for video recording (for Colab or headless environments).

3. Environment Exploration
- Created and explored the LunarLander-v2 environment.
- Printed details of observation and action spaces.

4. Vectorized Environment
- Created a vectorized environment with 16 parallel instances for diverse experience during training.

5. DQN Implementation
- Defined the Q-network architecture using PyTorch.
- Implemented a replay buffer for storing experiences.
- Built the DQN agent class with epsilon-greedy action selection, learning, target network updates, and epsilon decay.

6. Training Setup
- Checked for GPU availability and set the device accordingly.
- Initialized the environment and agent.
- Set training parameters: number of episodes, max timesteps, etc.

7. Agent Training
- Trained the DQN agent over 2000 episodes.
- Stored rewards and decayed epsilon after each episode.
- Saved the model every 100 episodes.

8. Performance Visualization
- Plotted the total reward per episode to visualize learning progress.
- Displayed key hyperparameters below the plot.

9. Agent Evaluation
- Loaded the trained model and evaluated it on new episodes.
- Calculated and printed mean and standard deviation of rewards.
