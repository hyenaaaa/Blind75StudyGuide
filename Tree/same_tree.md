**Problem:** Same Tree

**Difficulty:** Easy

**Description:** Given the roots of two binary trees p and q, write a function to check if they are the same or not. Two binary trees are considered the same if they are structurally identical, and the nodes have the same value.

**Explanation:**
This one is pretty straightforward and not too bad. We need to find if both trees have the same structure and have the same values. To do this the easiest way is using recursion helper function. We will store the "structure" in two separate lists and compare them at the end. We then call our helper function on each list and each tree. In the helper function, it will be set up like most traversal helper functions. First, we check if it's nullptr (None) and if it is we need to append -1 to our list (think structure) and return. Otherwise we add the node's value to our list and traverse pre-order through the tree. Then in our main function, we just return the comparison of the two and should get either true or false.


**Code(Python)**:

* Runtime: O(n)
```Python
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def value_to_list(self, node, val_list):
        # check if we are at the end of our tree, if so add a -1 place holder and return
        if node == None:
            val_list.append(-1)
            return
        
        # traverse pre-order to get all the nodes (this traversal method doesn't matter)
        val_list.append(node.val)

        self.value_to_list(node.left, val_list)
        self.value_to_list(node.right, val_list)

    def isSameTree(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:
        list_1, list_2 = [], []

        # call both recursive functions on each list/tree
        self.value_to_list(p, list_1)
        self.value_to_list(q, list_2)

        # return comparison between the two lists, if the same that means they are structured the same
        return list_1 == list_2
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
