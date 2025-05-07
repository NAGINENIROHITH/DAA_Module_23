# EX 5B Coin Change Problem
## DATE:
## AIM:
To compute the fewest number of coins that we need to make up the amount given.


## Algorithm
1. Initialization:

   Create a DP array dp of size amount + 1, initialized with -1, representing that the amount is currently unreachable.

   Set dp[i] = 1 for all coin values i that are ≤ amount.

2. Edge Case Checks:

   If amount is 0, return 0 (no coins needed).

  If the minimum coin is greater than amount, return -1 (no solution possible).

3. Bottom-Up DP Table Construction:

  For each coin, iterate from coin + 1 to amount.

  If dp[j - coin] != -1, it means amount j - coin is reachable, so update dp[j]:

  If dp[j] == -1, set it to dp[j - coin] + 1.

  Else, set it to min(dp[j], dp[j - coin] + 1) to keep the minimum count.

4. Result Extraction:
   After filling the DP table, dp[amount] gives the minimum number of coins required to make the amount.

5. Return Result:
   If dp[amount] == -1, no combination is possible; otherwise, return dp[amount].

## Program:
```
/*
Create a python function to compute the fewest number of coins that we need to make up the amount given.
Developed by: NAGINENI ROHITH
Register Number:  212222040105
*/
```
```
class Solution(object):
   def coinChange(self, coins, amount):
      if amount == 0 :
         return 0
      if min(coins) > amount:
         return -1
      dp = [-1 for i in range(0, amount + 1)]
      for i in coins:
         if i > len(dp) - 1:
            continue
         dp[i] = 1
         for j in range(i + 1, amount + 1):
            if dp[j - i] == -1:
               continue
            elif dp[j] == -1:
               dp[j] = dp[j - i] + 1
            else:
               dp[j] = min(dp[j], dp[j - i] + 1)
         #print(dp)
      return dp[amount]
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))


print(ob1.coinChange(s,amt))
```
## Output:
![image](https://github.com/user-attachments/assets/6f16d357-3303-454c-a20e-9f86e69eb06e)


## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
