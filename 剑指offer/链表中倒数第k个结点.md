#### 输入一个链表，输出该链表中倒数第k个结点。
思路：设定两个指针，第一个从链表头到链表尾遍历，第一个大于k时，第二个也开始跟着第一个一起向后遍历，直到第一个指针到链表尾，第二个指针就到了第k个数那地方。
```cpp
#include <iostream>
#include <stdio.h>
#include <stdlib.h>
using namespace std;


struct ListNode {
	int val;
	struct ListNode *next;
	ListNode(int x) :
			val(x), next(NULL) {
	}
};

class Solution {
public:
    ListNode* ListCreate(ListNode* N){
        ListNode* Head = N;
        for(int i = 0;i < 5;i++){
           ListNode* P = (ListNode*)malloc(sizeof(struct ListNode));
           scanf("%d",&P->val);
           P->next = N->next;
           N->next = P;
        }
        return Head;
    }

    ListNode* FindKthToTail(ListNode* pListHead, unsigned int k) {
        if(pListHead == NULL||k == 0)
            return NULL;
        ListNode* pre = pListHead;
        ListNode* p = pListHead;
        for(int i = 1;i < k;i++){
            if(pre->next != NULL)
                pre = pre->next;
            else
                return NULL;
        }
        while(pre->next != NULL){
            pre = pre->next;
            p = p->next;
        }
        return p;
    }
};

int main()
{
    Solution S;
    ListNode* L = (ListNode*)malloc(sizeof(struct ListNode));
    L->next = NULL;
    ListNode* H = S.ListCreate(L);
    cout <<S.FindKthToTail(H,1)->val<< endl;
    return 0;
}
```
