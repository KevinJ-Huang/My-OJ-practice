```cpp

struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    vector<vector<int> > levelOrder(TreeNode *root) {
        vector<vector<int> > res;
        queue<TreeNode*> st;
        vector<int> alist;
        if(!root)
            return res;
        st.push(root);
        while(!st.empty()){
            alist.clear();
            int n = st.size();
            for(int i = 0;i < n;i++){
                TreeNode *cur = st.front();
                st.pop();
                alist.push_back(cur->val);
                if(cur->left)
                    st.push(cur->left);
                if(cur->right)
                    st.push(cur->right);
            }
            res.push_back(alist);
        }
        return res;
    }
};

```
