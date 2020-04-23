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
    void reorderList(ListNode *head) {
        if(head == NULL||head->next == NULL||head->next->next==NULL){
            return;
        }
        ListNode *fast = head;
        ListNode *slow = head;
        while(fast->next&&fast->next->next){
            fast = fast->next->next;
            slow = slow->next;
        }
        fast = slow->next;
        slow->next = NULL;
        while(fast){
            ListNode *temp = fast->next;
            fast->next = slow->next;
            slow->next = fast;
            fast = temp;
        }
        ListNode *p = head;
        ListNode *q = slow->next;
        while(p&&q){
            slow->next = q->next;
            q->next = p->next;
            p->next = q;
            p = q->next;
            q = slow->next;
        }
    }
};

```
