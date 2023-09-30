# hello-drl-world
First deep reinforcement learning library, working through the easier Gymnasium Classic Control and Box2D environments, and closely following Laura Graesser and Wah Loon Keng's book Foundations of Deep Reinforcement Learning and accompanying environment, SLM Lab. 

## DRL Algorithms
| Agent | Implemented? | Type | Pros | Cons | Notes |
| :---: | :---: | :---: | :---: | :---: | :---: |
| REINFORCE | ✓ | Policy Gradient | - Smooth action probability distribution (vs e.g. discontinuous e-greedy) <br> - Policy potentially simpler function to approximate than value functions <br> - Can approach deterministic policy | - High variance (without baseline) <br> - Sample inefficient <br>  -No guarantee of efficient exploration | Only simplest version implemented: next implement version with baseline  |
| SARSA |  |  |  |  |  |
| DQN |  |  |  |  |  |
| A2C |  |  |  |  |  |
| PPO |  |  |  |  |  |
| A3C |  |  |  |  |  |

## Agent-Environment implementation
| Environment | Type | Training start | Training end | REINFORCE | SARSA | DQN | A2C | PPO | A3C | 
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Cartpole | Classic Control | ![](./media/cartpole_unsolved.gif) | ![](./media/cartpole_solved.gif) | ✓ |  |  |  |  |
| Pendulum | Classic Control |  |  |  |  |  |  |  |
| Mountain Car (Disc) | Classic Control |  |  |  |  |  |  |  |
| Acrobot | Classic Control |  |  |  |  |  |  |  |
| Lunar Lander | Box2D |  |  |  |  |  |  |  |
| Bipedal Walker | Box2D |  |  |  |  |  |  |  |

## Nomenclature
| Symbol | Meaning |
| :---: | :---: |
| $\tau$ | **Trajectory**: a sequence of state-action-rewards, $s_0, a_0, r_0, ..., s_T, a_T, r_T$, sampled from a policy, $\tau \sim \pi$ |
| $\pi_{\theta}$ | **Policy (parametrised)**: A function which outputs stochastic actions, given a state: $a \sim \pi(s)$. Neural net used as function approximator, with learnable parameters $\theta$ |
| $R(\tau)$ | Return of a trajectory (at time step 0; if mid-way through an episode, subscripted by t; $R_t(\tau)$ |
| $J(\pi_{\theta})$ | Objective function: expected return over all trajectories generated by an agent |
| $\nabla_{\theta}J(\pi_{\theta})$ | Policy gradient: used in gradient ascent update equation to maximise the objective |
| `session` | **Level 0**: Initialisation and training of RL agent using specific set of hyperparameters and random seed |
| `trial` | **Level 1**: Multiple sessions: same hyperparameters, different random seeds |
| `experiment` | **Level 2**: Different sets of hyperparameters, with a trial for each one |
