# Smart Agriculture with Federated Learning and Reinforcement Learning

This project implements a **Smart Farming System** that leverages **Federated Learning (FL)** and **Reinforcement Learning (RL)** to optimize agricultural practices and make data-driven decisions for improving crop yields.

The system integrates **machine learning**, **data preprocessing**, and **decision-making models** to simulate real-world farming scenarios and provide actionable insights.

---

## Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
  - [Federated Learning Model](#federated-learning-model)
  - [Reinforcement Learning Environment](#reinforcement-learning-environment)
  - [Smart Farming Decision System](#smart-farming-decision-system)
- [Dataset](#dataset)
- [Results](#results)
- [Contributing](#contributing)

---

## Features
- **Federated Learning**:
  - Trains models locally on multiple simulated farms (`farm1`, `farm2`, `farm3`) and averages their weights to update a global model.
  - Predicts crop yield based on environmental parameters like temperature, rainfall, and soil pH.
- **Reinforcement Learning**:
  - Implements a custom environment (`FarmEnv`) to optimize farming actions such as irrigation, fertilization, and monitoring.
  - Trains a Q-learning model to maximize total rewards by taking the best action based on the current state.
- **Smart Farming Decision System**:
  - Combines predictions from the FL model with the RL model to recommend optimal farming actions with confidence levels.

---

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Wadu-TT/PBL.git
   cd PBL
   ```
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage
1. Open the Jupyter Notebook:
   ```bash
   jupyter notebook agri.ipynb
   ```
2. Run the cells sequentially to:
   - Install and import required libraries.
   - Load and preprocess the dataset.
   - Train the Federated Learning and Reinforcement Learning models.
   - Make smart farming decisions based on user input.

---

## How It Works

### Federated Learning Model
The FL model simulates decentralized training across multiple farms:
- Each farm trains a local model using its own data.
- The local models' weights are averaged to update a global model.
- This process is repeated for multiple rounds to minimize the global loss.

**Key Functions**:
- `FLModel`: Class to build, train, and update the global FL model.
- `federated_average`: Method to average the weights of local models.

### Reinforcement Learning Environment
The RL environment (`FarmEnv`) models farming actions and their rewards:
- States: `['optimal', 'suboptimal', 'critical']`
- Actions: `['irrigate', 'fertilize', 'monitor']`
- Rewards: Defined based on the state and action taken.

The Q-learning algorithm trains a policy to maximize cumulative rewards:
- Updates the Q-table using the Bellman equation.
- Balances exploration and exploitation using an epsilon-greedy policy.

### Smart Farming Decision System
The decision system combines predictions from the FL model with the RL model:
- Predicts crop yield based on input parameters (temperature, rainfall, soil pH).
- Recommends the best farming action based on the current state of the farm.
- Outputs the predicted yield, recommended action, and decision confidence.

**Example Output**:
```
=== Smart Farming Decision ===
Predicted Yield: 43.9%
Recommended Action: IRRIGATE
Decision Confidence: 262.8%
```

---

## Dataset
1. **Seed Dataset**:
   - Source: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/machine-learning-databases/00236/seeds_dataset.txt)
   - Features:
     - `area`, `perimeter`, `compactness`, `kernel_length`, `kernel_width`, `asymmetry`, `groove_length`, `class`

2. **Synthetic Data**:
   - Generated for federated learning:
     - `Temperature`, `Rainfall`, `Soil_pH`, `Yield`

### Data Preprocessing:
- Standardized features using `StandardScaler`.
- Encoded categorical labels using `LabelEncoder`.

---

## Results
### Federated Learning Progress:
The loss decreases over 10 rounds, demonstrating effective model training across farms.

### Reinforcement Learning Progress:
The RL agent learns an optimal policy to maximize rewards over 100 episodes.

### Smart Farming Decision:
The system provides actionable recommendations with high confidence based on trained models.

---

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your changes.

---

