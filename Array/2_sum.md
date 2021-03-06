**Problem:** 2sum

**Difficulty:** Easy

**Description:** Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target. You may assume that each input would have exactly one solution, and you may not use the same element twice. You can return the answer in any order.

**Explanation:**
For this problem we are trying to get the optimal time complexity which is O(n). If we attempt to brute force it using two for loops, we will get the correct answer, but the time complexity will be O(n^2) which is quite slow. This is a good starting point so we can set ourselves up for the optimal solution.

Doing the optimal solution is much better as we will achieve O(n) for time complexity since we are only going to loop over the vector once! We start off by using an unordered_map and a vector to return. We then are able to loop over the vector once using a for loop, and if the target minus the number is in our map (that we are adding to) we can add that to our ans vector and return. Otherwise, we just add that element to our map. The map is structured as the following, integer, index position(also integer). That way we can keep track of it as we iterate through our vector.


**Code(Python)**:

* Runtime: O(n)
```Python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # dictionary to use later
        required = {}

        # iterate through the length of our list
        for i in range(len(nums)):
            # if the number we need is in our dictionary, return the indices
            if target-nums[i] in required:
                return [required[target-nums[i]], i]
            # otherwise, put it in our dictionary
            else:
                required[nums[i]] = i
```

**Code(C++)**:
* Runtime: O(n^2)
```C++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int size = nums.size();
        vector<int> ans;
        
        // loop over vector twice to look through all combinations.
        for(int i=0; i < size; ++i) {
            for(int j = i+1; j < size; ++j) {
                // target found, return the index positions..
                if(nums[i] + nums[j] ==  target) {
                    ans.push_back(i);
                    ans.push_back(j);
                    // we could also just return {i, j}
                    return ans;
                }
            }
        }
        // if nothing found, return empty vector.
        return ans;
    }
};
```

* Runtime: O(n)
```C++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> m;
        vector<int> ans;
        int size = nums.size();
        
        for(int i = 0; i < size; ++i) {
            // if we find a match in our hash map, push both indices.
            if(m.find(target-nums[i]) != m.end()) {
                ans.push_back(m[target-nums[i]]);
                ans.push_back(i);
                
                return ans;
            }
            // otherwise, add it to our hash map.
            else{
                m[nums[i]] = i;
            }
        }
        return ans;
    }
};
```
