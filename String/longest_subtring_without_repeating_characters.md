**Problem:** Longest Substring Without Repeating Characters

**Difficulty:** Medium

**Description:** Given a string s, find the length of the longest substring without repeating characters.

**Explanation:**
This one is pretty difficult at first glance but gets easier the more you look and understand it. The main thing we are going to use here it the sliding window method. We will need two points for this, a right and a left pointer. We are also going to use a set because sets cannot have repeat characters and our goal is to find the longest substring without repeating characters. So we use a while loop and first we check if the right pointer is in our set, if it is then we are going to remove the left pointer character from the set and increment the left pointer by one. Otherwise, we are going to add right pointer's character to the set, increment the right pointer and get the max of our output integer compare to the difference of right and left.


**Code(Python)**:

* Runtime: O(n)
```Python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        # setup our set and pointers and output integer
        count_characters = set()
        right, left, output = 0, 0, 0

        # we will go until the right point is at the end of the string
        while right < len(s):
            # if that character is in our set, we remove it from the set and
            # increment our left pointer
            if s[right] in count_characters:
                count_characters.remove(s[left])
                left += 1
            # otherwise, we add it to our set, increment the right pointer and get the max of right minus the left (longest substring)
            else:
                count_characters.add(s[right])
                right += 1
                output = max(output, right - left)
            
        return output
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
