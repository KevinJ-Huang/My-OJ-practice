```cpp

struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    vector<vector<int> > pathSum(TreeNode *root, int sum) {
        vector<vector<int> > res;
        vector<int> cur;
        collect(root,sum,res,cur);
        return res;
    }
    void collect(TreeNode *root, int sum,vector<vector<int> > &res,vector<int> cur){
        if(!root)
            return ;
        cur.push_back(root->val);
        if(!root->left&&!root->right&&root->val==sum)
            res.push_back(cur);
        collect(root->left,sum-root->val,res,cur);
        collect(root->right,sum-root->val,res,cur);
    }
};




```
