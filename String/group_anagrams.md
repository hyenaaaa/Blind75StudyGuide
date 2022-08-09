**Problem:** Group Anagrams

**Difficulty:** Medium

**Description:** Given an array of strings strs, group the anagrams together. You can return the answer in any order. An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Explanation:**
This problem is a little hard to wrap your head around at first. We start off with a dictionary that is defaulted with lists. We then iterate through our list of strings and start by initializing a list with 26 spaces each with zero this will represent the occurrence of a character. We then go through each character and count its occurrence. After we are done we add to our result dictionary with the count list we had earlier as the key and the string as the values, and we append this incase we get multiple.


**Code(Python)**:

* Runtime: O(n * m)
```Python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        result = defaultdict(list)

        for s in strs:
            # store occurrences
            count = [0] * 26

            # iterate through and add them to our count list
            for char in s:
                count[ord(char) - ord('a')] += 1
            
            # add the occurrences as the key and the string to the value (list)
            result[tuple(count)].append(s)

        # return all the values which are the string grouped by occurrences
        return result.values()
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
