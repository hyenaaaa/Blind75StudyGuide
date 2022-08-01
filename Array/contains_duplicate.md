**Problem:** Contains Duplicate

**Difficulty:** Easy

**Description:** Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

**Explanation:**
This problem is a little on the easier side. To simplify this a lot, first we can create a copy of the list and convert it to a *set* which removes all duplicates because sets CANNOT have those. Then all we need to do is compare the length of the set and the length of the list. Since it's asking to return true if there is a duplicate, we must switch the logic and use *!=* instead of *==*.


**Code(Python)**:

* Runtime: O(n)
```Python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        # set removes all duplicate numbers
        compare_list = set(nums)

        # compare the length of the two, return true if there is a duplicate and false otherwise.
        return len(compare_list) != len(nums)
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
