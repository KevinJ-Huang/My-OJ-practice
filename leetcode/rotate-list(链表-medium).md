```cpp
struct ListNode {
   int val;
   ListNode *next;
   ListNode(int x) : val(x), next(NULL) {}
};

class Solution {
public:
    ListNode *rotateRight(ListNode *head, int k) {
        if(!head)
            return NULL;
        ListNode *cur = head;
        int n = 1;
        while(cur->next){
            n++;
            cur = cur->next;
        }
        cur->next = head;
        int m = n-k%n;
        for(int i = 0;i < m;i++)
            cur = cur->next;
        ListNode *newhead = cur->next;
        cur->next = NULL;
        return newhead;
    }
};


```
