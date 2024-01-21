---
title: "Neural Tactics and AI Theory"
date: 2019-01-28T15:15:26+10:00
weight: 2
---

This project delves into the realm of data science and artificial intelligence to tackle the strategic optimization of game theory using Q-learning. Through iterative learning and data-driven decision-making, the initiative aims to enhance the gameplay of an AI agent. It encapsulates the core data science process: collecting game state data, learning from this data through reinforcement learning, and validating the strategy through extensive simulation and statistical analysis.

![QLearning VS Deep Q Learning](https://i.ibb.co/V3j3KsF/Screenshot-from-2024-01-20-22-07-37.png)

## Abstract

The classical game of Nim, with its roots in mathematical strategy, provides a fertile ground for advancing computational intelligence and game theory through artificial intelligence (AI). This project harnesses Q-learning, a model-free reinforcement learning algorithm, to develop an AI that can master the intricacies of Nim. Unlike traditional approaches that rely on pre-existing datasets, our AI agent actively generates its own data through gameplay, which constitutes state-action-reward sequences. These sequences are then used to update the Q-table, serving as the agent's evolving knowledge base.

The project's focus is on the AI's ability to learn and refine its strategies through continuous interaction with the game environment. By analyzing the changes in the Q-table and monitoring the win rates against both random and deterministic "guru" opponents, we gain insights into the AI's learning patterns, including its adaptability and any potential plateaus in performance. Through statistical methods and data visualization techniques, we chart the agent's progression, highlighting the dynamic balance between exploration of new strategies and exploitation of known tactics.

Our approach demonstrates how AI can engage with classic games in a data-driven manner, optimizing decision-making processes without the need for an external dataset. This self-sufficient learning mechanism underscores the potential of integrating game theory with neural tactics in AI, paving the way for further research into strategic AI applications. The project exemplifies the convergence of theoretical principles and practical algorithmic implementation, contributing to the discourse on AI's role in strategic gameplay and beyond.

## Objectives

1. **Strategic AI Development:** To program an AI that can master Nim through Q-learning, capable of adjusting strategies in response to game dynamics.
    
2. **Performance Optimization:** To enhance the AI's gameplay by iteratively improving win rates against both random and expert opponents.

3. **Analytical Visualization:** To utilize data visualization techniques for depicting the AI's learning progression and strategy effectiveness over time.

## Relevance

The relevance of this project lies in its intersection with data science, AI, and game theory. Nim, a game grounded in mathematical strategy, provides a perfect testbed for reinforcement learning algorithms. This project contributes to the field of data science by demonstrating how machine learning can be applied to strategic decision-making, offering insights that extend beyond gaming into areas such as optimization problems and economic modeling.

## Methodology

The methodology of this project is structured around a data science lifecycle, which consists of the following steps:

1. **Algorithm Design and Implementation:** The core of the project is the design of the Q-learning algorithm, which is implemented to interact with the game environment of Nim. Q-learning is a type of model-free reinforcement learning algorithm that learns a policy dictating the best action to take given the current state.

2. **Data Generation:** Instead of using a pre-existing dataset, the project generates its own data through simulations. Every game played between the AI agents (Qlearner, Random, and Guru) generates state-action-reward sequences that are stored and used to update the Q-table, which effectively becomes the dataset.

3. **Learning Process:** The Q-table, representing the state-action space of the Nim game, is iteratively updated as the AI agents play each game. The Q-values are adjusted using the reward signals received, with the goal of maximizing future rewards. This represents the AI's learning process from the generated data.

4. **Performance Evaluation and Analysis:** The evaluation of the AI's strategy is performed through statistical analysis of win rates across a number of simulated games. This measures the effectiveness of the learned strategies and the AI's ability to adapt and improve over time.

5. **Data Visualization:** The results of the performance evaluation are visualized using matplotlib to create plots that depict the learning progression and win rates. These visualizations serve as a tool for interpreting the data and extracting insights about the AI's learning trajectory.

6. **Iterative Optimization:** Based on the insights gained from the performance evaluation and data analysis, the learning parameters such as Alpha (learning rate) and Gamma (discount factor) are fine-tuned to optimize the AI's gameplay.

By focusing on the continuous cycle of gameplay simulation, data generation, strategy evaluation, and visualization, the project embodies a data science approach to developing AI game strategies.

## Results

QLearner vs Random (Winning Start Position)

| Training Sessions | QLearner Wins | Random Wins |
|-------------------|---------------|-------------|
| 3                 | 5204          | 4796        |
| 10                | 5312          | 4688        |
| 100               | 7653          | 2347        |
| 1000              | 9219          | 781         |
| 10000             | 9919          | 81          |
| 50000             | 9983          | 17          |
| 100000            | 9989          | 11          |


QLearner vs Guru (Winning Start Position)

| Training Sessions | QLearner Wins | Guru Wins |
|-------------------|---------------|-----------|
| 3                 | 46            | 9954      |
| 10                | 33            | 9967      |
| 100               | 87            | 9913      |
| 1000              | 464           | 9536      |
| 10000             | 3631          | 6369      |
| 50000             | 8074          | 1926      |
| 100000            | 9246          | 754       |

Random vs QLearner (Losing Start Position)

| Training Sessions | Random Wins | QLearner Wins |
|-------------------|-------------|---------------|
| 3                 | 4685        | 5315          |
| 10                | 3994        | 6006          |
| 100               | 2513        | 7487          |
| 1000              | 983         | 9017          |
| 10000             | 175         | 9825          |
| 50000             | 75          | 9925          |
| 100000            | 72          | 9928          |

Guru vs QLearner (Losing Start Position)

| Training Sessions | Guru Wins | QLearner Wins |
|-------------------|-----------|---------------|
| 3                 | 9993      | 7             |
| 10                | 9989      | 11            |
| 100               | 9975      | 25            |
| 1000              | 9877      | 123           |
| 10000             | 9568      | 432           |
| 50000             | 9405      | 595           |
| 100000            | 9379      | 621           |



## Data Visualization

![Qlearner Performance Comparison in Winning Starting Position](https://i.ibb.co/xgvTbWC/Screenshot-from-2024-01-21-01-57-19.png)

![Qlearner Performance Comparison in Losing Starting Position](https://i.ibb.co/xCbzTkP/Screenshot-from-2024-01-21-01-57-52.png)


## Analysis

The results presented in the two charts depict the performance of a Q-learning AI in the game of Nim across various training games, measured by the win rate against two types of opponents: Random and Guru. In the context of these charts, the term 'Guru' likely refers to a strategy that plays optimally or near-optimally.


The first chart, illustrating the "Winning Starting Position," shows an overall increasing trend in win rate against the Random opponent, plateauing at high win rates. This demonstrates the Q-learner's ability to exploit the randomness and mistakes of the non-strategic opponent from a position of advantage. However, against the Guru, the win rate increases initially but then drops significantly at the higher number of training games. A possible interpretation is that as the Q-learner becomes more deterministic in its strategy through learning, it becomes predictable and easier for the Guru to counter, especially if the Guru employs a strategy based on the Q-learner's moves.

Meanwhile, in the second chart, representing the "Losing Starting Position," there is a noticeable slow trend of win rate starting in the latter half as the number of training games crosses the 1000 mark when facing the Guru opponent. This could suggest that the Q-learner is struggling to find a winning strategy at the beginning against an opponent that likely has a deterministic advantage from the start, but as the number of games is increasing after 1000 games, the win rate slowly increases as well. Against the Random opponent, the Q-learner's performance remains high throughout, indicating that the AI can capitalize on the non-deterministic nature of its opponent, despite the initial disadvantage.


## Conclusion

From these observations, it is apparent that the Q-learning AI is quite effective against opponents with non-deterministic strategies (Random) but faces challenges when up against a deterministic and possibly strategic opponent (Guru), especially when the Q-learner starts from a disadvantaged position. The performance against the Random opponent is consistently high, suggesting that the AI is successfully learning strategies that exploit the randomness and lack of optimality in the Random opponent's play.

Against the Guru, the AI initially learns effective strategies, as indicated by the increase in win rate, but this trend does not hold in the long run when the AI is in the winning starting position. This could be due to the Q-learner converging on a suboptimal deterministic strategy that the Guru can exploit.

These insights could lead to several actionable steps for improving the Q-learning algorithm:

- **Strategy Diversification:** Introducing non-deterministic elements or noise into the Q-learner's strategy to make it less predictable against strategic opponents.
- **Opponent Modeling:** Incorporating models of the opponent's strategy into the Q-learner to better anticipate and counter strategic plays.
- **Hyperparameter Tuning:** Adjusting the learning rate (Alpha) and discount factor (Gamma) to see if slower or faster learning affects the AI's ability to adapt to strategic opponents.

In summary, the Q-learning AI shows promise in learning effective strategies for the game of Nim, especially from a strong starting position and against non-strategic opponents. However, there is room for improvement, particularly in games where the AI starts at a disadvantage and against opponents with deterministic strategies.

## Faithful Representation:

The project ensures faithful representation by accurately reporting the AI's performance without bias. The win rates and learning curves are presented as-is, with no manipulation of the data, providing an honest depiction of the AI's capabilities and limitations.

## Comparability:

Comparability is maintained by consistently evaluating the AI against the same opponents and under the same conditions throughout the training process. This allows for a fair comparison of performance across different numbers of training games and provides reliable insights into the learning progress.

## Understandability:

To ensure understandability, the project presents data and findings in a clear, concise manner, with graphical visualizations that simplify complex concepts. Detailed annotations and explanations accompany each plot and statistical result, making the project's insights accessible to both technical and non-technical audiences.


### Source Code

The project is publicly available on my [Github Repository](https://github.com/malsuwailm/neural-tactics-and-AI-theory) and is open for further contributions.
