```cpp

struct TreeLinkNode {
  int val;
  TreeLinkNode *left, *right, *next;
  TreeLinkNode(int x) : val(x), left(NULL), right(NULL), next(NULL) {}
};
 
class Solution {
public:
    void connect(TreeLinkNode *root) {
        if(!root||!root->right||!root->left)
            return ;
        else{
            TreeLinkNode *p = root, *q;
            while(p->left){
                q = p;
                while(q){
                    q->left->next = q->right;
                    if(q->next)
                        q->right->next = q->next->left;
                    q = q->next;
                }
                p = p->left;
            }
        }
    }
};
```
