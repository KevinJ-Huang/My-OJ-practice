```cpp


struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    int sumNumbers(TreeNode *root) {
        int sum = 0;
        if(!root)
            return sum;
        return ordersum(root,sum);
    }
    int ordersum(TreeNode *root,int sum){
        if(!root)
            return 0;
        sum = sum*10+root->val;
        if(!root->left&&!root->right)
            return sum;
        return ordersum(root->left,sum)+ordersum(root->right,sum);
    }
};



```
