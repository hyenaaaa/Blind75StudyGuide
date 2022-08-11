**Problem:** Merge Two Sorted Lists

**Difficulty:** Easy

**Description:** You are given the heads of two sorted linked lists list1 and list2. Merge the two lists in a one sorted list. The list should be made by splicing together the nodes of the first two lists. Return the head of the merged linked list.

**Explanation:**
<text here>


**Code(Python)**:

* Runtime: O(n)
```Python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode()
        curr = dummy

        # iterate through both linked list until one of them ends
        while list1 and list2:
            # find lowest of both linked in lists
            if list1.val < list2.val:
                curr.next = list1
                list1 = list1.next
            else:
                curr.next = list2
                list2 = list2.next
            # iterate to next of our current so we can update it
            curr = curr.next

        # if while loop ends, one of our linked lists aren't empty, so we must add to our curr linked list
        if list1:
            curr.next = list1
        elif list2:
            curr.next = list2

        return dummy.next

```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
