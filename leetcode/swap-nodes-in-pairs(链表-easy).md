```cpp

struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(NULL) {}
 };

class Solution {
public:
    ListNode *swapPairs(ListNode *head) {
        if(!head||!head->next)
            return head;
        ListNode L(-1);
        L.next = head;
        ListNode *f = &L;
        ListNode *p = head;
        while(p&&p->next){
            ListNode *q = p->next;
            p->next = q->next;
            q->next = p;
            f->next = q;
            f = p;
            p = p->next;
        }
        return L.next;
    }
};


```
