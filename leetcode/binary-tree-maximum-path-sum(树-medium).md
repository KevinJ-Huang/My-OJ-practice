```cpp
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    int maxPathSum(TreeNode *root) {
        int res = INT_MIN;
        DFS(root,res);
        return res; 
    }
    int DFS(TreeNode* root,int& res){
        if(!root) return 0;
        int left = max(DFS(root->left,res),0);
        int right = max(DFS(root->right,res),0);
        res = max(res,left+right+root->val);
        return max(root->val+left,root->val+right);
    }
};



```
