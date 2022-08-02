**Problem:** Validate Binary Search Tree

**Difficulty:** Medium

**Description:** Given the root of a binary tree, determine if it is a valid binary search tree (BST). 

A valid BST is defined as follows:
* The left subtree of a node contains only nodes with keys less than the node's key.
* The right subtree of a node contains only nodes with keys greater than the node's key.
* Both the left and right subtrees must also be binary search trees.

**Explanation:**
This one seems intimidating at first but isn't bad at all. Our task is to validate this BST. I know the best way to do that is to traverse through it using *in-order* traversal. We start off with a list and then call our helper function which is going to do most of the work. In the helper function we are just going traverse as normal making sure to append the data between the two function calls. After that we will be back in our main function. Next, we need to make sure that the value ahead of the current is always greater than the first. We can iterate through our list and check to see if the current element is greater than or equal to the next element, and if so return false. Otherwise it's a valid BST and we return true!


**Code(Python)**:

* Runtime: O(n)
```Python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def traverse_tree(self, node, t_list):
        if node == None:
            return
        
        # traverse in-order and add to our list.
        self.traverse_tree(node.left, t_list)

        t_list.append(node.val)

        self.traverse_tree(node.right, t_list)

    def isValidBST(self, root: Optional[TreeNode]) -> bool:
        node_list = []

        # we will traverse in-order through the tree
        self.traverse_tree(root, node_list)

        # here we make sure that current element isn't greater than or equal the next one
        for i in range(len(node_list) - 1):
            if node_list[i] => node_list[i + 1]:
                return False
        
        return True
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
