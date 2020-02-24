```cpp

 //递归
class Solution {
public:
    vector<int> preorderTraversal(TreeNode *root) {
        vector<int> res;
        PreOrder(root,res);
        return res;
    }
    void PreOrder(TreeNode *root,vector<int> &res){
        if(!root)
             return;
        res.push_back(root->val);
        PreOrder(root->left,res);
        PreOrder(root->right,res);
    }
};
//非递归
class Solution {
public:
    vector<int> preorderTraversal(TreeNode *root) {
        vector<int> res;
        stack<TreeNode*> st;
        st.push(root);
        while(root&&!st.empty()){
            TreeNode *cur = st.top();
            st.pop();
            res.push_back(cur->val);
            if(cur->right)
                st.push(cur->right);
            if(cur->left)
                st.push(cur->left);
            
        }
        return res;
    }
};

```
