**Problem:** Top K Frequent Elements

**Difficulty:** Medium

**Description:** Given an integer array nums and an integer k, return the k most frequent elements. You may return the answer in any order.

**Explanation:**
For this problem we will have to work around *k*, and use bucket array. First, we start out with a dictionary and a list of lists which has as many lists as length of our nums list. Then we fill our dictionary with each number in our nums list and count the number of occurrences. Now we have a dictionary which has a number corresponding to its count. Next, we need to iterate through this dictionary and add it to our frequency list. We do this because there could be multiple numbers with the same count, we append them so that each count has its own "bucket". After doing this we can finally build the result list and return it. Since we want the maximum frequencies, we must iterate backwards over this list of lists. Starting from the highest count, we iterate through all of the numbers in that bucket appending them to our result list. After we're done appending, we check to see if the length is equal to k and if so we return!


**Code(Python)**:

* Runtime: 
```Python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        # initialize the counter dictionary and list of lists for frequencies
        number_counter = {}
        freq = [[] for n in range(len(nums) + 1)]

        # iterate through our nums list and add that to our number_counter
        for n in nums:
            number_counter[n] = 1 + number_counter.get(n, 0)
        
        # now iterate through our dictionary and append them to each frequency bucket
        for num, count in number_counter.items():
            freq[count].append(num)
        
        result = []
        # lastly, we iterate backwards through the list of lists (buckets) and go through each bucket adding each of those number to our result list
        for i in range(len(freq) - 1, 0, -1):
            for num in freq[i]:
                result.append(num)
            # after appending to our result list, if the length of it is equal to k, that is when we return
            if len(result) == k:
                return result


```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
