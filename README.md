# 90.-magic-square
import numpy as np
import sys

order = int(input("Enter order of magic square (order must be odd): "))

# if even number is given then it will be incremented by one
if order % 2 == 0:
    order = order + 1
    print("Given order is even so it is incremented by 1.")

mid = order // 2

magic = np.zeros((order, order), dtype=int)

k = mid
j = 0

for i in range(1, order * order + 1):
    magic[j][k] = i
    p = j
    q = k

    j = j - 1
    k = k + 1

    if j < 0:
        j = order - 1

    if k > order - 1:
        k = 0

    if magic[j][k] != 0:
        j = p + 1
        k = q

print("Generated Magic Square is:\n")

for j in range(order):
    print("|", end="")
    for k in range(order):
        print("%4d |" % magic[j][k], end="")
    print()
    for i in range(1, 6 * order + 1):
        print("-", end="")
    print()
output:
|   8 |   1 |   6 |
------------------
|   3 |   5 |   7 |
------------------
|   4 |   9 |   2 |
------------------
