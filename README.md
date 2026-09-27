# CliffWalking Game Using SARSA Reinforcement Learning

## About the Project

This project explores Reinforcement Learning by training an agent to navigate the **CliffWalking environment using the SARSA algorithm**.

The goal is simple: the agent needs to travel from the starting point to the destination without falling off a cliff. However, the agent doesn't know the correct path initially. It learns through trial and error, receiving rewards and penalties for its actions.

Through this project, I wanted to understand how an agent learns from its own experiences and how reinforcement learning can help it make better decisions over time.

## How the Game Works

CliffWalking is a grid-based environment available in the Gymnasium library.

* The environment consists of a 4 × 12 grid.
* The agent starts in the bottom-left corner.
* The goal is to reach the bottom-right corner.
* The cells between the starting point and the goal on the bottom row represent a cliff.
* The agent can move up, down, left or right.

The agent receives a reward of **-1 for each step**. If it falls into the cliff, it receives a penalty of **-100** and returns to the starting position.

The challenge is to find a path that reaches the goal while avoiding the cliff and minimizing unnecessary steps.

## Understanding SARSA

SARSA stands for State–Action–Reward–State–Action. It is an on-policy reinforcement learning algorithm that learns from the actions the agent actually takes.

The learning process follows five steps:

1. Observe the current state.
2. Choose an action using an epsilon-greedy strategy.
3. Perform the action and receive a reward.
4. Observe the next state and choose the next action.
5. Update the Q-value using the SARSA equation.

**SARSA update equation:**

Q(s, a) ← Q(s, a) + α [r + γ Q(s', a') − Q(s, a)]

Where:

* α (Alpha): Learning rate
* γ (Gamma): Discount factor
* r: Reward received
* Q(s, a): Current Q-value
* Q(s', a'): Q-value of the next state and chosen action

SARSA learns from the policy it follows, including its exploratory actions. This makes it particularly interesting for CliffWalking, where exploring near the cliff can lead to large penalties.

## Technologies Used

* Python
* Jupyter Notebook
* Gymnasium
* NumPy

## Training the Agent

Initially, the agent explores the environment and makes random decisions. Sometimes it moves toward the goal, while other times it falls into the cliff.

I used an epsilon-greedy strategy to balance exploration and exploitation. During exploration, the agent tries different actions. During exploitation, it chooses actions based on the Q-values it has learned.

After multiple episodes, the agent updates its Q-table and gradually learns which actions lead to better long-term rewards.

## What I Learned

Working on this project helped me understand:

* How reinforcement learning agents interact with an environment.
* How the SARSA algorithm updates Q-values.
* The importance of balancing exploration and exploitation.
* How rewards and penalties influence an agent's decisions.
* Why a safer path can sometimes be preferable to the shortest path.

One of the most interesting aspects of SARSA is that it accounts for the risks associated with exploration. In CliffWalking, this can encourage the agent to learn a route farther away from the cliff.

## How to Run the Project

Clone the repository:

```bash
git clone https://github.com/ShwetaKumari-programming/Reinforcement-project.git
```

Navigate to the project directory:

```bash
cd Reinforcement-project
```

Install the required libraries:

```bash
pip install gymnasium numpy matplotlib notebook
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open `SARSA.ipynb` and run the cells in sequence.

## Future Improvements

I plan to experiment with different learning rates, discount factors and exploration strategies to see how they affect the agent's performance.

I would also like to compare SARSA with Q-learning to understand the differences between on-policy and off-policy reinforcement learning.

## Conclusion

This project was a practical introduction to reinforcement learning. Instead of programming every movement, I trained an agent to learn from its own actions and improve through experience.

CliffWalking helped me understand how intelligent agents make decisions when their actions involve both rewards and risks.

---

