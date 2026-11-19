
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
https://alphbeta.bytexl.live/
