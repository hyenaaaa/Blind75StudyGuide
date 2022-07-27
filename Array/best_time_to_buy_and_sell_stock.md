**Problem:** Best Time to Buy and Sell Stock

**Difficulty:** Easy

**Description:** You are given an array prices where prices[i] is the price of a given stock on the ith day. You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock. Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

**Explanation:**
In this problem, we first initialize two variables for the maximum and minimum prices. The minimum price is initalized to infinity. Then we iterate through our prices list. We begin with calculating the minimum, and then get the profit taking the price minus the minimum price. After that, we take the max of the maximum price and the profit. By the end of our loop, we return the maximum price as that will be the maximum profit.


**Code(Python)**:

* Runtime: O(n)
```Python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # initialize max and min
        min_price = float('inf')
        max_price = 0

        # loop through our prices list
        for price in prices:
            # grab minimum price
            min_price = min(min_price, price)

            # calculate profit
            profit = price - min_price

            # grab maximum of our max price and profit
            max_price = max(max_price, profit)
        
        return max_price

```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
