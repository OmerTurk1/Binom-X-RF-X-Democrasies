# Analyzing Collective Decision Accuracy Using Probabilistic Models

This project explores how the accuracy of a group decision—made through majority voting—changes depending on the individual accuracy **(p)** of each decision-maker and the group size **(n)**.  
The goal is to mathematically and visually examine how collective judgments can outperform individual judgments under certain conditions.

---

## 🎯 Purpose

- To model the **probability of a correct majority decision** given individual correctness probabilities.  
- To analyze how collective accuracy changes with different values of **p** and **n**.  
- To visualize these outcomes and connect them to **democratic decision-making systems**.  

---

## 📐 1. Mathematical Foundation

Each member of a group makes a binary decision with individual correctness probability:

\[
p
\]

Group size:

\[
n
\]

The probability that the majority of the group makes the correct decision is:

\[
P(\text{majority correct}) = 
\sum_{r=\lceil n/2 \rceil}^{n} 
\binom{n}{r} \, p^{r} (1-p)^{n-r}
\]

The notebook implements:

- A factorial-based combination function  
- A binomial probability function (`binom`)  
- A `calculate` function that sums all outcomes in which the majority is correct  

---

## 🧪 2. Simulation Range

The simulation evaluates collective accuracy across the following parameter ranges:

- **Individual accuracy (p):** 0.50 → 0.80  
- **Group size (n):** 3 → 50  

For each pair \((p, n)\), the probability of a correct majority decision is computed and stored.

---

## 📊 3. Visualization

Using **seaborn**, results are visualized as a heatmap:

- **X-axis:** Individual accuracy (p)  
- **Y-axis:** Group size (n)  
- **Color scale:** Probability that the majority decision is correct  

This visualization clearly illustrates how both parameters influence collective performance.

---

## 📈 Findings

### 🔹 1. Slightly-above-random accuracy leads to highly accurate group decisions  
If individual accuracy is even a bit above 0.5, large groups tend to make highly reliable decisions.  
This behavior reflects the **Condorcet Jury Theorem**.

### 🔹 2. Larger groups greatly improve decision reliability  
Collective accuracy increases sharply with group size, even when individuals are only moderately reliable.

### 🔹 3. When individual accuracy is close to 0.5, improvement is limited  
If voters behave nearly randomly, increasing group size alone does not significantly improve accuracy.

---

## 🗳️ Implications for Democracy

This model provides strong theoretical insights into democratic systems and majority voting:

### ✔ 1. *“Wisdom of the crowd” is mathematically valid*  
As long as individuals are **more likely than not** to choose correctly, majority decisions become increasingly accurate.

### ✔ 2. Larger electorates make fewer systematic errors  
High participation improves decision quality at the societal scale.

### ✔ 3. Poor information environments can be dangerous  
If misinformation pushes individual accuracy below 0.5:

- collective decisions become systematically wrong,  
- and even very large groups cannot recover reliability.

### ✔ 4. Democracies require informed citizens  
Education, transparency, and factual information keep the value of **p** above the critical threshold needed for functioning democratic decision-making.

---

