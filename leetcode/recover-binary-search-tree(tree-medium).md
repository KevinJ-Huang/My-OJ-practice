```cpp
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    void inorder(TreeNode*root, TreeNode**pre, TreeNode**first, TreeNode**second){
        if (root==nullptr)
            return;
        inorder(root->left, pre, first, second);
        if (*pre!=nullptr && (*pre)->val>root->val){
            if (*first==nullptr){
                *first = *pre;
            }
            *second = root;
        }
        *pre = root;
        inorder(root->right, pre, first, second);
    }
    void recoverTree(TreeNode *root) {
        if (root==nullptr)
            return;
        TreeNode*first = nullptr,*second = nullptr, *pre = nullptr;
        inorder(root, &pre, &first, &second);
        if (first!=nullptr && second !=nullptr)
            swap(first->val,second->val);
    }
};


```
