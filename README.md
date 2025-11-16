Analyzing Collective Decision Accuracy Using Probabilistic Models

This project explores how the accuracy of a group decision—made through majority voting—changes depending on the individual accuracy (p) of each decision-maker and the group size (n). The goal is to mathematically and visually examine how collective judgments can outperform individual judgments under certain conditions.

🎯 Purpose

To model the probability of a correct majority decision given individual correctness probabilities.
To analyze how collective accuracy changes with different values of *p* and *n*.
To visualize these outcomes and connect them to democratic decision-making systems.

1. Mathematical Foundation

Each member of a group makes a binary decision with individual correctness probability:
p
and group size:
n
The probability that the majority of the group makes the correct decision is:

𝑃
(
majority correct
)
=
∑
𝑟
=
⌈
𝑛
/
2
⌉
𝑛
(
𝑛
𝑟
)
 
𝑝
𝑟
(
1
−
𝑝
)
𝑛
−
𝑟
P(majority correct)=
r=⌈n/2⌉
∑
n
	​

(
r
n
	​

)p
r
(1−p)
n−r

The notebook implements:
factorial-based combination function,
binomial probability function (binom),
calculate function that sums over all outcomes where the majority is correct.

2. Simulation Range

The simulation covers:
Individual accuracy p: 0.50 to 0.80
Group size n: 3 to 50
For each pair (p,n), the collective accuracy is computed and stored.

3. Visualization

Using seaborn, the results are displayed as a heatmap:
X-axis: individual accuracy (p)
Y-axis: group size (n)
Cell color: probability that the majority decision is correct
This visualization reveals how both parameters influence collective performance.

📊 Findings
🔹 1. If individual accuracy is even slightly above 0.5, large groups tend to be highly accurate.
This behavior confirms the well-known Condorcet Jury Theorem.
🔹 2. Increasing group size dramatically boosts decision reliability.
🔹 3. If individual accuracy is too close to 0.5, even large groups provide limited improvement.

🗳️ Implications for Democracy

The model provides powerful insights into democratic systems and majority voting:
✔ 1. “Wisdom of the crowd” is mathematically sound
As long as individuals are more likely than not to choose correctly, the group’s majority decision becomes increasingly accurate.
✔ 2. Larger electorates make fewer errors
High participation enhances correctness on a system-wide scale.
✔ 3. However, poor information can be dangerous
When misinformation lowers individual accuracy below 0.5:
collective decisions become systematically wrong,
even very large groups cannot compensate.
✔ 4. Democracies require informed citizens
Education, transparency, and access to accurate information are essential.
They keep the individual correctness probability p above the critical threshold needed for majority decisions to function effectively.
