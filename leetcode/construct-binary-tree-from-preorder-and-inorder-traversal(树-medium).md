```cpp

struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    TreeNode *buildTree(vector<int> &preorder, vector<int> &inorder) {
        return build(preorder,inorder,0,preorder.size()-1,0,inorder.size()-1);
    }
    TreeNode *build(vector<int> &preorder, vector<int> &inorder,int l1,int r1,int l2,int r2){
        if(l1>r1)
            return NULL;
        int cnt = 0,value = preorder[l1], i;
        for(i = l2;i <= r2&&inorder[i]!=value;i++)
            cnt++;
        TreeNode *root = (TreeNode *)malloc(sizeof(TreeNode));
        root->val = value;
        root->left = build(preorder,inorder,l1+1,l1+cnt,l2,i-1);
        root->right = build(preorder,inorder,l1+cnt+1,r1,i+1,r2);
        return root;
    }
};

```
