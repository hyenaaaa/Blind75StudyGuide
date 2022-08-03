**Problem:** Valid Anagram

**Difficulty:** Easy

**Description:** Given two strings s and t, return true if t is an anagram of s, and false otherwise. An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Explanation:**
The first solution is rather simple and relies mostly on the sorted function in python to just sort all the letter in the strings and compare them.

The next solution is more suited for an interview. First we make two dictionaries so we can count the occurrences of each letter. We loop through each string and get all of that information. The only thing left to do is compare them and return that result!


**Code(Python)**:

* Runtime: O(nlogn)
```Python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return sorted(s) == sorted(t)
```

* Runtime: O(n)
```Python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        # define our two dictionaries
        dict1 = {}
        dict2 = {}

        # iterate through each string and get the count of the characters
        for char in s:
            dict1[char] = 1 + dict1.get(char, 0)
        for char in t:
            dict2[char] = 1 + dict2.get(char, 0)
        
        # compare and return
        return dict1 == dict2
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
