```cpp


struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(NULL) {}
};

class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        if(!head)
            return 0;
        ListNode *slow = head;
        ListNode *fast = head;
        while(fast&&fast->next){
            fast = fast->next->next;
            slow = slow->next;
            if(fast == slow)
                break;
        }
        if(!fast||!fast->next)
            return NULL;
        slow = head;
        while(slow!=fast){
            fast = fast->next;
            slow = slow->next;
        }
        return slow;
    }
};





```
