```cpp

class Solution {
public:
    int run(TreeNode *root) {
        if(!root)
            return 0;
        if(!root->left)
            return run(root->right)+1;
        if(!root->right)
            return run(root->left)+1;
        return min(run(root->right)+1,run(root->left)+1);
    }
};

```
