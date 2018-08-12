#### 给定一棵二叉搜索树，请找出其中的第k小的结点。例如， （5，3，7，2，4，6，8）    中，按结点数值大小顺序第三小结点的值为4。
思路：最简单的想法，进行中序遍历，然后找到第k大的数。

```cpp
#include <iostream>

using namespace std;


struct TreeNode {
    int val;
    struct TreeNode *left;
    struct TreeNode *right;
    TreeNode(int x) :
            val(x), left(NULL), right(NULL) {
    }
};

class Solution {
int count=0;
public:
    TreeNode* KthNode(TreeNode* pRoot, int k)
    {
        if(pRoot==NULL)
           return NULL;
        vector<TreeNode*> vec;
        InOrder(pRoot,vec);
        if(k>vec.size())
           return NULL;
        return vec[k-1];
    }
    void InOrder(TreeNode* pRoot,vector<TreeNode*>& vec){
        if(pRoot==NULL)
           return;
        InOrder(pRoot->left,vec);
        vec.push_back(pRoot);
        InOrder(pRoot->right,vec);
    }
};

int main()
{
    cout << "Hello world!" << endl;
    return 0;
}

```
