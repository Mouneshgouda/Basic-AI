
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
Alpha-Beta Pruning Algorithm
1. Game Tree
                  MAX
                 /   \
               MIN   MIN
              /  \   /  \
             3    5 6    9

2. Step-by-Step Explanation
Step 1: Initialize Alpha and Beta

Initially,

Alpha = -∞
Beta  = +∞

Alpha (α): Best value for MAX.
Beta (β): Best value for MIN.
Step 2: First MIN Node

Terminal values are 3 and 5.

MIN chooses the smallest value:

MIN(3, 5) = 3


MAX updates Alpha:

α = 3
β = +∞

Step 3: Second MIN Node

Terminal values are 6 and 9.

MIN chooses the smallest value:

MIN(6, 9) = 6


MAX updates Alpha:

α = max(3, 6) = 6
β = +∞

Step 4: Find the Final Answer

MAX chooses the largest value:

MAX(3, 6) = 6


Final Answer: 6

3. Pruning Condition
If Alpha >= Beta:
    Stop checking the remaining branches.


In this example, no pruning occurs because all four terminal values are checked.

4. Conclusion

Alpha-Beta Pruning improves the Minimax algorithm by skipping unnecessary branches. It produces the same final result as Minimax while potentially reducing the number of nodes evaluated.

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
