**Problem:** Maximum Subarray

**Difficulty:** Medium

**Description:** Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum. A subarray is a contiguous part of an array.

**Explanation:**
This one is quite difficult to understand at first. Here we need to find the *contiguous* subarray (all touching) that has the maximum sum. This seems impossible at first and can lead us down a rabbit hole if we are not careful. The goal here is to make sure we only do one pass of the list instead of multiple like you might think at first (brute force).

To start out, we can first iterate over the nums length starting at one so we can check the element behind the current. Then if the element behind the current is greater than one, we add it to our current because this positively increases our sum, negative numbers are bad. Once we are done going through all the numbers in the list, one of those numbers will be our maximum "sum" which is the answer we want. To find this easily, we can use the max function in Python and find the largest one in the list and return!

Here's an example using [-2, 1, -2, 4, -1, 2, 1, -5, 4]:

Start: 1

Start: -3
Adding 1 to -3
[-2, 1, -2, 4, -1, 2, 1, -5, 4]
Start: 4

Start: -1
Adding 4 to -1
[-2, 1, -2, 4, 3, 2, 1, -5, 4]

Start: 2
Adding 3 to 2
[-2, 1, -2, 4, 3, 5, 1, -5, 4]

Start: 1
Adding 5 to 1
[-2, 1, -2, 4, 3, 5, 6, -5, 4]

Start: -5
Adding 6 to -5
[-2, 1, -2, 4, 3, 5, 6, 1, 4]

Start: 4
Adding 1 to 4
[-2, 1, -2, 4, 3, 5, 6, 1, 5] --> end!


**Code(Python)**:

* Runtime: O(n)
```Python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        for i in range(1, len(nums)):
            if nums[i-1] > 0:
                nums[i] += nums[i-1]
        return max(nums)
```

```Python
class Solution:

```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
