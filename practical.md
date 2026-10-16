
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
