```cpp

struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    TreeNode *buildTree(vector<int> &inorder, vector<int> &postorder) {
        return build(inorder,postorder,0,inorder.size()-1,0,postorder.size()-1);
    }
    TreeNode *build(vector<int> &inorder,vector<int> &postorder,int l1,int r1,int l2,int r2){
        if(l1 > r1)
            return NULL;
        int value = postorder[r2],mid = l1,cnt = l2;
        TreeNode *root = (TreeNode *)malloc(sizeof(TreeNode));
        for(int i = l1;i <= r1;i++){
            if(value == inorder[i])
                break;
            mid++;
            cnt++;
        }
        root->val = value;
        root->left = build(inorder,postorder,l1,mid-1,l2,cnt-1);
        root->right = build(inorder,postorder,mid+1,r1,cnt,r2-1);
        return root;
    }
};


```
