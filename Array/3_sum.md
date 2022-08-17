**Problem:** 3 Sum

**Difficulty:** Medium

**Description:** Given an integer array nums, return all the triplets [nums[i], nums[j], nums[k]] such that i != j, i != k, and j != k, and nums[i] + nums[j] + nums[k] == 0. Notice that the solution set must not contain duplicate triplets.

**Explanation:**
This one is very tricky and different from 2 sum. The key here is to *sort* the array. Once we sort it we can iterate through our nums list. First we make sure that the previous number isn't the same as the current one. After that is finished, we can set our left and right pointers. Then we need another loop so we can change our left and right pointers based on the sum. First we calculate the sum which is easy enough! Then if it's greater than zero, we decrease our right pointer because it's sorted we need a smaller number. Same thing for the left pointer if it's lower than zero, we increase left to get a greater number. Otherwise, we have found a sum that equals zero! We append this to our result list and increase our left pointer. Then the thing we have to be careful for is that our left pointer isn't the same as the previous. Because of this, we have to loop through until we don't get a match and increase our left pointer if we do! We also will make sure to not go over our right pointer.


**Code(Python)**:

* Runtime: O(n^2)
```Python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        result = []
        nums.sort()

        # for every index, value in nums
        for i, a in enumerate(nums):
            # make sure our pointer doesn't have same value for 'a'
            if i > 0 and a == nums[i - 1]:
                continue
            
            # set left and right pointers
            left, right = i + 1, len(nums) - 1

            while left < right:
                three_sum = a + nums[left] + nums[right]

                # since it's sorted and greater, then we decrease right pointer to get a lesser number
                if three_sum > 0:
                    right -= 1
                # since it's sorted and less, then we increase left pointer to get a greater number
                elif three_sum < 0:
                    left += 1
                # we found it equals zero!
                else:
                    result.append([a, nums[left], nums[right]])
                    left += 1

                    while nums[left] == nums[left - 1] and left < right:
                        left += 1
        
        return result
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
