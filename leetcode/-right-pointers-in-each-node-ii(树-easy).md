```cpp

struct TreeLinkNode {
    int val;
    TreeLinkNode *left, *right, *next;
    TreeLinkNode(int x) : val(x), left(NULL), right(NULL), next(NULL) {}
};

class Solution {
public:
    void connect(TreeLinkNode *root) {
        while(root){
            TreeLinkNode f(-1), *cur;
            cur = &f;
            for(auto p = root;p;p = p->next){
                if(p->left){
                    cur->next = p->left;
                    cur = cur->next;
                }
                if(p->right){
                    cur->next = p->right;
                    cur = cur->next;
                }
            }
            root = f.next;
        }
    }
};


```
