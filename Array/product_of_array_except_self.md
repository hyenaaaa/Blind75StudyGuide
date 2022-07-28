**Problem:** Product of Array Except Self

**Difficulty:** Medium

**Description:** Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i].The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer. You must write an algorithm that runs in O(n) time and without using the division operation.

**Explanation:**
This is a tricky one as we are unable to use division because this would be very easy just take the product and divide by the nums[i], and we are restricted to O(n) time. So this brings us to our new algorithm involving prefix and postfix calculations. To also make this O(1) space, we can just modify one list that we will be able to return at the end. First, we declare our results list with '1' placeholder with a length of nums. Then we initialize prefix to 1 and begin iterating forward through our nums list. We then set the result[i] equal to our prefix, while our prefix changes and is multiplied by nums[i] as this needs to change everytime. After we are done setting up all the prefix spots in the results list, we need to do the same, but going backwards through the list. This time we multiply the result[i] with the postfix, and then multiply our postfix with nums[i]. This will then end up with all of our values set in place and multiplied correctly.


**Code(Python)**:

* Runtime: O(2n) == O(n)
```Python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        # create result list with 1 placeholder size of nums list.
        result = [1] * len(nums)

        prefix = 1
        for i in range(len(nums)):
            result[i] = prefix
            prefix *= nums[i]

        postfix = 1
        # iterate backwards through our nums array starting at the last element
        # range(total steps, starting, step amount), or we could use: reversed(range(len(nums)))
        for i in range(len(nums) - 1, -1, -1):
            result[i] *= postfix
            postfix *= nums[i]

        return result

```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
