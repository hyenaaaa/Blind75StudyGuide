**Problem:** Maximum Product Subarray

**Difficulty:** Medium

**Description:** Given an integer array nums, find a contiguous non-empty subarray within the array that has the largest product, and return the product. The test cases are generated so that the answer will fit in a 32-bit integer. A subarray is a *contiguous* subsequence of the array.

**Explanation:**
This is very similar to the last question we just did, but this time we are using multiplication instead of adding. If we follow the same process as the last one, it will work, but not all the time. There are some things to think about. If we multiply starting from left->right, we might encounter an odd number of negative numbers that might influence all the other numbers to become negative and we might *miss* some of the positive numbers that are at the end. This is when reversing the list helps, because if we go through it both ways we are sure not to miss it. Also, instead of checking if the number behind the current is greater than zero, this time we will be making sure it's not one. This is because one will wipe out our max and doesn't contribute anything.


**Code(Python)**:

* Runtime: 
```Python
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        # reverse the list
        rev_nums = nums[::-1]

        # traverse through the same way, but this time forward & back
        for i in range(1, len(nums)):
            # make sure we don't encounter a zero, doesn't contribute.
            if nums[i-1] != 0:
                nums[i] *= nums[i-1]
            if rev_nums[i-1] != 0:
                rev_nums[i] *= rev_nums[i-1]
        
        # we then return the max we get from both of the lists.
        return max(nums + rev_nums)


```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
