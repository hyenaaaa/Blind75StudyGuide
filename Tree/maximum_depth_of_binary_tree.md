**Problem:** Maximum Depth of Binary Tree

**Difficulty:** Easy

**Description:** Given the root of a binary tree, return its maximum depth. A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

**Explanation:**
This one is rather simple to understand. First we check if root is None (nullptr) and return zero if so which means the tree was empty. Next, we go recursively through each direction and get the count.


**Code(Python)**:

* Runtime: O(n)
```Python
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        # if we reach the end of our tree
        if root == None:
            return 0
        
        # get the count of going left or right
        left_count = self.maxDepth(root.left)
        right_count = self.maxDepth(root.right)

        # compare these counts against each other and increment each by 1 (to account for the head)
        if left_count > right_count:
            return left_count + 1
        else:
            return right_count + 1
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
