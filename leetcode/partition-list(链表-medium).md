```cpp
struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(NULL) {}
};

class Solution {
public:
    ListNode *partition(ListNode *head, int x) {
        ListNode *head1 = new ListNode(-1);
        ListNode *head2 = new ListNode(-1);
        ListNode *p = head1;
        ListNode *q = head2;
        while(head){
            if(head->val < x){
                p->next = head;
                p = p->next;
            }
            else{
                q->next = head;
                q = q->next;
            }
            head = head->next;
        }
        q->next = NULL;
        p->next = head2->next;
        return head1->next;
    }
};





```
