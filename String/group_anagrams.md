**Problem:** Group Anagrams

**Difficulty:** Medium

**Description:** Given an array of strings strs, group the anagrams together. You can return the answer in any order. An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Explanation:**
<text here>


**Code(Python)**:

* Runtime: 
```Python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        result = defaultdict(list)

        for s in strs:
            count = [0] * 26

            for char in s:
                count[ord(char) - ord('a')] += 1
            
            result[tuple(count)].append(s)
 
        return result.values()
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
