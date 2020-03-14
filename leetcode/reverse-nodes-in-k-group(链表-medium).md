```cpp

struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(NULL) {}
};

class Solution {
public:
    ListNode *reverseKGroup(ListNode *head, int k) {
        if(!head||!head->next||k<2)
            return head;
        ListNode *p = head,*tmp = head,*next;
        ListNode f(-1);
        f.next = head;
        
        for(int i = 0;i < k;i++){
            if(!p)
                return head;
            p = p->next;
        }
        
        next = p;
        while(head->next!=next){
            tmp = head->next;
            head->next = tmp->next;
            tmp->next = f.next;
            f.next = tmp;
        }
        head->next = reverseKGroup(next,k);
        return f.next;
    }
};



```
