22091313:04
Status:  #KAT
Tags: 

# Cooperation and Competition
***Competition*** - The goal is maximising own gains at the cost of gains of other agents.
	All *constant-sum* and 0-sum games are competitive.
	**Matching pennies** is a single game in which two players: Even and Odd choose head or tails (1 or 0). It is a purely competitive game, as either of the players win.
***Cooperation*** - The goal is achieving the best utility for every agent
	A *general-sum* game is not a constant-sum game. There are situations in which both agents loose and those in which both agents win
***Mixed motives*** – Mix between competition and cooperation. 
	A restaurant picking game – A game with cooperative elements in which agents differ in their preferences. 

**[[Nash equilibrium]]** describes a stable solution of a game. No agent can increase their score by unilaterally (done by one agent) changing their strategy. 
	Points of Nash equilibrium can consist of multiple score levels.
***[[Pareto Efficient]] outcomes*** – an outcome is Pareto efficient if no agent can achieve a higher utility without decreasing the utility of another.
	- It does not guarantee the highest social welfare.
	- It is not fair.
**Dominated strategy** – A strategy which doesn't result in the optimal outcome in any case. A strategy is dominated if there always exist a course of actions which results in higher payoff no matter what the opponent does. A rational agent never chooses a dominated strategy. It can be used while finding [[Nash equilibrium]]
[[Prisoner's dilemma]] – Two prisoners are offered a plea bargain.
	- Defect on their partner in return for reduced jail time.
	- Without a confession, jail time will be low.
	- With both confessions, jail time will increase for both.
	- In repeated prisoner's dilemma, it is more efficient to cooperate.

## [[Axelrod's tournament]]
Each agent learn a policy $\pi_i$ 
These are either RANDOM, ALL-D, ALL-C, TIT-FOR-TAT, JOSS, GRIM

**Fictitious play** counts opponent's action frequencies $P(a_j)$ and plays the best response
	If policies converge, Nash equilibrium is reached ^ba0c55

**Joint action learning** – suppose the utilities of actions are not actually known
$Q(a_i, a_j) \leftarrow (1-\alpha)(a_i, a_j) + \alpha r$ where $\alpha$ is a learning rate 

**Conditional joint action learning** – suppose the utilities of actions are not actually known.
	- Solution: use Q-learning to model utility

**Stochastic games** consists of:
- Set of sates $s$
- Set of agents $N = \{1, \dots, n\}$

**Game** is a mathematical model of strategic interaction.

***WoLF-PHC - Win-or-Learn-Fast Policy Hill Climbing***

### Multi-agent teamwork

**Ad-hoc teamwork**

- Many algorithms quietly assume self-play
- Algorithms based on reinforcement leaning learn the behaviour of others from scratch
- Middle ground – type-based learning
	- cannot rely on self-play
	- RL needs thousands of iterations even in simple games
	- Type-based learning provides a middle ground

---
# References