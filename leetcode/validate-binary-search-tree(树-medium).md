```cpp


struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    bool isValidBST(TreeNode *root) {
        return isValidRoot(root,INT_MAX,INT_MIN); 
    }
    bool isValidRoot(TreeNode *root,int up,int down){
        if(!root)
            return true;
        if(root->val >= up||root->val <= down)
            return false;
        return isValidRoot(root->left,root->val,down)&&isValidRoot(root->right,up,root->val);
    }
};



```
