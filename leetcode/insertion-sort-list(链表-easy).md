```cpp
struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(NULL) {}
};

class Solution {
public:
    ListNode *insertionSortList(ListNode *head) {
        ListNode *dumpy = new ListNode(-1), *cur = dumpy;
        while(head){
            ListNode *p = head->next;
            cur = dumpy;
            while(cur->next&&head->val>=cur->next->val)
                cur = cur->next;
            head->next = cur->next;
            cur->next = head;
            head = p;
        }
        return dumpy->next;
    }
};



```
