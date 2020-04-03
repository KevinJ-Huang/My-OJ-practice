```cpp

struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    vector<vector<int> > zigzagLevelOrder(TreeNode *root) {
        vector<vector<int> > res;
        if(!root)
            return res;
        vector<int> alist;
        queue<TreeNode*> st;
        st.push(root);
        bool flag = false;
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
            if(flag)
                reverse(alist.begin(),alist.end());
            flag = !flag;
            res.push_back(alist);
        }
        return res;
    }
};




```
