```cpp

/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *mergeTwoLists(ListNode *l1, ListNode *l2) {
        if(!l1) return l2;
        if(!l2) return l1;
        ListNode *p = new ListNode(-1);
        ListNode *q = p;
        while(l1&&l2){
            if(l1->val>l2->val){
                p->next = l2;
                p = p->next;
                l2 = l2->next;
            }
            else{
                p->next = l1;
                p = p->next;
                l1 = l1->next;
            }

        }
        p->next = (l1)?l1:l2;
        return q->next;
    }
};

```
