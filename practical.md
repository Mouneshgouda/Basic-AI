
```python
A = [1, 2, 3]
B = [1, 2, 3]
C = [1, 2, 3]

for a in A:
    for b in B:
        for c in C:
            if a != b and b != c and a != c:
                print("A =", a, "B =", b, "C =", c)
                break
        else:
            continue
        break
    else:
        continue
    break

```
🌳 Alpha-Beta Pruning Algorithm
📌 Overview

Alpha-Beta Pruning is an optimization technique for the Minimax algorithm used in two-player games. It reduces the number of nodes evaluated in the game tree by eliminating branches that cannot influence the final decision.

It produces the same optimal result as Minimax while potentially improving performance.

🌲 Game Tree

Consider the following game tree, where MAX tries to maximize the score and MIN tries to minimize it.

                MAX
               /   \
             MIN   MIN
            /  \   /  \
           3    5 6    9

🔵 MAX: Chooses the maximum value.
🔴 MIN: Chooses the minimum value.
✂️ Pruning: Skips branches that cannot affect the final result.
⚙️ Step-by-Step Explanation
Step 1: Initialize Alpha and Beta

Initially, set:

Alpha (α) = −∞ — The best value MAX can guarantee so far.
Beta (β) = +∞ — The best value MIN can guarantee so far.
Step 2: Evaluate the First MIN Node

The first MIN node has two terminal values: 3 and 5.

MIN selects the smaller value:

min
⁡
(
3
,
5
)
=
3

MAX updates its best value:

𝛼
=
max
⁡
(
−
∞
,
3
)
=
3

Current values:

Alpha (α) = 3
Beta (β) = +∞
Step 3: Evaluate the Second MIN Node

The second MIN node has two terminal values: 6 and 9.

MIN selects the smaller value:

min
⁡
(
6
,
9
)
=
6

MAX updates its best value:

𝛼
=
max
⁡
(
3
,
6
)
=
6

Current values:

Alpha (α) = 6
Beta (β) = +∞
Step 4: Determine the Final Result

MAX chooses the larger of the two MIN-node results:

max
⁡
(
3
,
6
)
=
6

🏆 Final Answer: 6

✂️ Pruning Condition

Alpha-Beta Pruning uses the following condition:

𝛼
≥
𝛽

When this condition is satisfied, the remaining branches of the current search can be skipped because they cannot change the final decision.

In this example: No pruning occurs because all four terminal nodes (3, 5, 6, and 9) are evaluated.

📊 Complexity Analysis
Case	Time Complexity
Worst case	
𝑂
(
𝑏
𝑑
)

Best case	
𝑂
(
𝑏
𝑑
/
2
)

Where:

b = branching factor (number of children per node)
d = maximum depth of the game tree

With good move ordering, Alpha-Beta Pruning can significantly reduce the number of nodes explored.

✅ Conclusion

Alpha-Beta Pruning improves the Minimax algorithm by eliminating unnecessary branches without changing the optimal result.

Key takeaways:

🎯 Finds the same optimal move as Minimax.
⚡ Reduces the number of nodes evaluated.
🌳 Uses Alpha (α) and Beta (β) to track bounds.
✂️ Prunes branches when α ≥ β.

In short: Alpha-Beta Pruning makes game-tree search more efficient by avoiding calculations that cannot affect the final decision.

```python
def alphabeta(depth, node, alpha, beta, is_max):
    if depth == 2:
        return node

    if is_max:
        best = -999
        for child in [3, 5]:
            val = alphabeta(depth + 1, child, alpha, beta, False)
            best = max(best, val)
            alpha = max(alpha, best)

            if alpha >= beta:
                break
        return best

    else:
        best = 999
        for child in [2, 4]:
            val = alphabeta(depth + 1, child, alpha, beta, True)
            best = min(best, val)
            beta = min(beta, best)

            if alpha >= beta:
                break
        return best

print("Best value:", alphabeta(0, 0, -999, 999, True))
```
