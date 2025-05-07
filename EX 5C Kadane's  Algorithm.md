# EX 5C Kadane's Algorithm
## DATE:
## AIM:
To write a python program to find the maximum contiguous subarray.


## Algorithm
1. Initialize Variables:

   Set max_so_far = a[0] to track the maximum sum found so far.

   Set max_ending_here = 0 to store the current subarray sum.

2. Iterate Through the Array:

    Loop through each element from index 0 to size - 1.

3.  Update Current Subarray Sum:

    Add the current element to max_ending_here.

4. Reset if Current Sum is Negative:

   If max_ending_here < 0, reset it to 0 (ignore the subarray).

5.  Update Maximum So Far:

   If max_ending_here > max_so_far, update max_so_far.

## Program:
```
/*
To implement the program to find the maximum contiguous subarray.
Developed by: NAGINENI ROHITH
Register Number:  212222040105
*/
```
```
def maxSubArraySum(a,size):
    max_so_far = a[0]
    max_ending_here = 0
    for i in range(0, size):
        max_ending_here = max_ending_here + a[i]
        if max_ending_here < 0:
            max_ending_here = 0
        elif (max_so_far < max_ending_here):
            max_so_far = max_ending_here
              
    return max_so_far
n=int(input())  
a =[] #[-2, -3, 4, -1, -2, 1, 5, -3]
for i in range(n):
    a.append(int(input()))
  
print("Maximum contiguous sum is", maxSubArraySum(a,n))
```

## Output:

![image](https://github.com/user-attachments/assets/dbcd2288-e7c0-430d-b440-8d29f4c301f0)


## Result:
Thus the program was executed successfully for finding the maximum contiguous sum of subarray..
