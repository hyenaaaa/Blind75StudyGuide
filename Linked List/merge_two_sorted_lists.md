**Problem:** Merge Two Sorted Lists

**Difficulty:** Easy

**Description:** You are given the heads of two sorted linked lists list1 and list2. Merge the two lists in a one sorted list. The list should be made by splicing together the nodes of the first two lists. Return the head of the merged linked list.

**Explanation:**
This one isn't that bad at first we just have to understand how it works. First, we initialize a dummy linked list that we will be returning in the end with both of our linked lists merged. Next we are going to use a while loop to loop over both linked lists until one of them reaches NULL. Next, we just check if list1's value is lower than list2's value then make our dummy list next be list1 and advance list1. Same goes for opposite and at the end of the loop we advance the dummy node to the next as well. Once one of the lists reach the end, we will take those remaining numbers and slap them on the end of the dummy list. Then we will return that list.


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
            # find lowest of both linked lists
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
