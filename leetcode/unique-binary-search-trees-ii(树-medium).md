```cpp
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    vector<TreeNode *> build(int left,int right){
        vector<TreeNode *> res;
        if(left > right){
            res.push_back(NULL);
            return res;
        }
        for(int i = left;i <=right;i++){
            vector<TreeNode *> leftpath = build(left,i-1);
            vector<TreeNode *> rightpath = build(i+1,right);
            for(int j = 0;j < leftpath.size();j++){
                for(int k = 0;k < rightpath.size();k++){
                    TreeNode *root = new TreeNode(i);
                    root->left = leftpath(j);
                    root->right = rightpath(k);
                    res.push_back(res); 
                }
            }
        }
        return res;
    }
    vector<TreeNode *> generateTrees(int n) {
        return build(1,n);
    }
};


```
