```cpp
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    bool isSymmetric(TreeNode *root) {
        if(!root)
            return true;
        return isSubSymmetric(root->left,root->right);
        
    }
    bool isSubSymmetric(TreeNode *left, TreeNode *right){
        if(!left&&!right)
            return true;
        if(!left||!right)
            return false;
        return (left->val==right->val)&&isSubSymmetric(left->left,right->right)&&isSubSymmetric(left->right,right->left);
    }
};

```
