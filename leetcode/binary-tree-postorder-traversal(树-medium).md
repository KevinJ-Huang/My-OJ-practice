```cpp

struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    vector<int> postorderTraversal(TreeNode *root) {
        vector<int> res;
        if(!root)
            return res;
        stack<TreeNode *> st;
        st.push(root);
        while(!st.empty()){
            TreeNode *temp = st.top();
            st.pop();
            res.push_back(temp->val);
            if(temp->left)
                st.push(temp->left);
            if(temp->right)
                st.push(temp->right);
        }
        reverse(res.begin(),res.end());
        return res;
    }
};



```
