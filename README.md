# Adaptive Entropy-Driven Umbrella Reinforcement Learning (AE-URL)

This repository contains the implementation of **Adaptive Entropy-Driven Umbrella Reinforcement Learning (AE-URL)**, a model-free hierarchical RL framework designed for scalable solutions to hard exploration and sparse-reward problems. The method combines adaptive entropy regularization, hindsight experience replay, and distributed training to achieve state-of-the-art performance on challenging RL benchmarks.

---

## Key Features
- **Model-Free Actor-Critic Architecture**: Eliminates dependency on environment dynamics using twin Q-networks and policy gradients.
- **Adaptive Entropy Regularization**: Dynamically balances exploration-exploitation via a learnable entropy coefficient.
- **Hierarchical Sub-Goal Decomposition**: Uses meta-policies and Hindsight Experience Replay (HER) to tackle sparse rewards.
- **Distributed Training**: Parallel ensemble simulations reduce wall-clock time by 42% while maintaining robustness.
- **Theoretical Guarantees**: Proven convergence with polynomial sample complexity in sparse-reward settings.

---

## Benchmark Results
AE-URL outperforms baselines (SAC, PPO, DreamerV3) on:
- **AntMaze**: 92% success rate (vs SAC’s 68%) with 42% fewer samples.
- **Montezuma’s Revenge**: 2.1× higher success rates than RND.
- **Humanoid-StandUp**: Solves task in 0.65 hours (vs 1.12 hours for SAC) using 16 workers.

| Method       | Success Rate | Steps to 90% | Training Time (h) |
|--------------|-------------|-------------|------------------|
| AE-URL       | **92%**     | **1.2M**    | **4.5**          |
| SAC          | 68%         | 2.1M        | 6.8              |
| URL (original)| 71%        | 1.9M        | 7.2              |

---

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/ae-url/AE-URL.git
   cd AE-URL
