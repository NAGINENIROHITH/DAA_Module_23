# EX 5D Minimum Jump to Reach End Array
## DATE:
## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.


## Algorithm
1. Initialize Jump Array:

    Create an array jumps[] of size n, where jumps[i] stores the minimum number of jumps needed to reach index i.

    Set jumps[0] = 0 as the starting point.

2. Edge Case Check:

    If the array is empty (n == 0) or the first element is 0, return infinity (can't move forward).

3. Traverse the Array:

    For each index i from 1 to n-1, find the minimum number of jumps needed to reach it.

4. Find Reachable Index:

    For each i, check all previous indices j such that i <= j + arr[j] (i.e., j can reach i).

    If reachable, update jumps[i] = min(jumps[i], jumps[j] + 1) and break (take the first valid path).

5. Return Result:

    Return jumps[n - 1] which stores the minimum jumps to reach the last index.  

## Program:
```
/*
To implement the program to finding the minimum number of jumps needed to reach end of the array.
Developed by: NAGINENI ROHITH
Register Number:  212222040105
*/
```
```
def minJumps(arr, n):
    jumps = [0 for i in range(n)]
 
    if (n == 0) or (arr[0] == 0):
        return float('inf')
 
    jumps[0] = 0
    for i in range(1, n):
        jumps[i] = float('inf')
        for j in range(i):
            if (i <= j + arr[j]) and (jumps[j] != float('inf')):
                jumps[i] = min(jumps[i], jumps[j] + 1)
                break
    return jumps[n-1]
arr = []
n = int(input()) #len(arr)
for i in range(n):
    arr.append(int(input()))
print('Minimum number of jumps to reach','end is', minJumps(arr,n))
 
```
## Output:
![image](https://github.com/user-attachments/assets/c3c9a49f-90c2-46cb-888d-789616420977)

## Result:
Thus the program was executed successfully for finding the minimum number of jumps to reach end.
