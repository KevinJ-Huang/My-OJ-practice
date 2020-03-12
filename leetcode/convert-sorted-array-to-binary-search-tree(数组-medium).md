```cpp

struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    TreeNode *sortedArrayToBST(vector<int> &num) {
        return BuildBST(num,0,num.size());
    }
    TreeNode *BuildBST(vector<int> &num,int start,int last){
        if(start >= last)
            return NULL;
        int mid = start + (last-start+1)/2;
        TreeNode *root = new TreeNode(num[mid]);
        root->left = BuildBST(num,start,mid);
        root->right = BuildBST(num,mid+1,last);
        return root;
    }
};


```
