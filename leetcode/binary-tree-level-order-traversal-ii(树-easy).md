```cpp
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    vector<vector<int> > levelOrderBottom(TreeNode *root) {
        queue<TreeNode*> st;
        vector<vector<int>> res;
        vector<int> cur;
        if(!root)
            return res;
        st.push(root);

        while(!st.empty()){
            cur.clear();
            int n = st.size();
            for(int i = 0;i < n;i++){
                TreeNode *t = st.front();
                st.pop();
                cur.push_back(t->val);
                if(t->left)
                    st.push(t->left);
                if(t->right)
                    st.push(t->right);
            }
            res.push_back(cur);
        }
        reverse(res.begin(),res.end());
        return res;
    }
};

```
