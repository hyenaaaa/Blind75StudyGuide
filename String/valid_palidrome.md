**Problem:** Valid Palindrome

**Difficulty:** Easy

**Description:** A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers. Given a string *s*, return true if it is a palindrome, or false otherwise.

**Explanation:**
This one isn't too bad. The thing that hard is understanding the question as it's written in a weird way that I didn't understand at first. It's asking you to take a string, remove all spaces, commas, etc. and just be left with lower case letters **and** numbers. The easiest thing I thought of was to build our string that we compare at the end. So first, we iterate through our initial string and ONLY add to our result string if it's a character or a number. We also make sure to change it to lowercase. Then at the end we just compare our result to a reverse copy, if both are the same it's a Palindrome!


**Code(Python)**:

* Runtime: O(n)
```Python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        result = ''

        # loop through our string character by character
        for i in range(len(s)):
            # if it's a character OR a number add it to our result string (lowercase)
            if s[i].isalnum():
                result += s[i].lower()
        
        # compare result string to a reverse result string
        return result == result[::-1]
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
