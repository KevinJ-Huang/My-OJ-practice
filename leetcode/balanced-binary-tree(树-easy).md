```cpp

 struct TreeNode {
     int val;
     TreeNode *left;
     TreeNode *right;
     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 };

class Solution {
public:
    bool isBalanced(TreeNode *root) {
        if(!root)
            return true;
        if(abs((MaxHeight(root->left)-MaxHeight(root->right)))>1)
            return false;
        return isBalanced(root->left)&&isBalanced(root->right);
        
    }
    int MaxHeight(TreeNode *root){
        if(!root)
            return 0;
        return max(MaxHeight(root->left)+1,MaxHeight(root->right)+1);
    }
};

```
