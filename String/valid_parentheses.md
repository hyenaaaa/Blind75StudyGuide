**Problem:** Valid Parentheses

**Difficulty:** Easy

**Description:** Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:
* Open brackets must be closed by the same type of brackets.
* Open brackets must be closed in the correct order.

**Explanation:**
This one isn't too bad and we can solve it using a stack! First we can define a dictionary that has the equivalent opening and closing brackets so we can reference later. Then we can iterate over the string. If the character is in the dictionary, then we can append it to our stack (opening bracket). Otherwise, the character is a closing bracket and we have to make sure the stack is greater than zero or if the top of the stack as a key to our dictionary is equal to the current character in our string. Then at the end we return the length of the stack to be zero incase we get an edge case if the string is just size one.


**Code(Python)**:

* Runtime: O(n)
```Python
class Solution:
    def isValid(self, s: str) -> bool:
        d = {'(': ')', 
             '{': '}', 
             '[': ']'}
        stack = []

        for i in range(len(s)):
            # if the character is an opening bracket, add to stack
            if s[i] in d:
                stack.append(s[i])
            # otherwise it's a closing bracket, pop it
            # if the stack is empty it's unbalanced, 
            # or if the closing bracket doesn't match the top of stack
            elif len(stack) == 0 or d[stack.pop()] != s[i]:
                return False
        
        # we return this due to edge case if string is one character
        return len(stack) == 0 
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
