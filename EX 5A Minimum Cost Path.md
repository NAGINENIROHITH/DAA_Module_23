# EX 5A Minimum Cost Path
## DATE:
## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.

## Algorithm
1. Base Conditions:
   If the current cell (m, n) is out of bounds (i.e., m < 0 or n < 0), return infinity (sys.maxsize) as this is an invalid path.
   If we are at the starting cell (0, 0), return its cost directly as the only cost.

2. Recursive Relation:
   For each cell (m, n), compute the cost to reach it from three possible directions:

   Top (m-1, n)

   Left (m, n-1)

   Diagonal Top-Left (m-1, n-1)

3. Compute Minimum Path Cost:
   Recursively find the minimum of the three possible previous paths and add the current cell’s cost.

4. Return Total Cost:
   Return the accumulated cost which includes the cost at (m, n) plus the minimum cost from any of the valid three directions.

5. Driver Execution:
   Input the desired destination coordinates (R-1, C-1) and call minCost(cost, R-1, C-1) to get the minimum cost path from (0, 0) to (R-1, C-1).
  

## Program:
```
/*
A program to implement to find the Minimum Cost Path Problem using a  Naive recursive Approach.

Developed by: NAGINENI ROHITH
Register Number: 212222040105  
*/
```
```
R = int(input())
C = int(input())
import sys
def minCost(cost, m, n):
    if (n < 0 or m < 0):
        return sys.maxsize
    elif (m == 0 and n == 0):
        return cost[m][n]
    else:
        return cost[m][n] + min( minCost(cost, m-1, n-1),
                                minCost(cost, m-1, n),
                                minCost(cost, m, n-1) )
def min(x, y, z):
    if (x < y):
        return x if (x < z) else z
    else:
        return y if (y < z) else z
cost= [ [1, 2, 3],
        [4, 8, 2],
        [1, 5, 3] ]
print(minCost(cost, R-1, C-1))
```
## Output:

![image](https://github.com/user-attachments/assets/25700216-bcb5-4c93-a345-8b14d1808de9)


## Result:
Thus the above program was executed successfully for finding the minimum cost.
