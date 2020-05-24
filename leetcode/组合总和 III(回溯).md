```cpp
class Solution {
public:
    vector<vector<int>> combinationSum3(int k, int n) {
        vector<vector<int>> res;
        if(n < 1||n > 45||k < 1)
            return res;
        vector<int> cur;
        DFS(res,cur,k,n,1);
        return res;
    }
    void DFS(vector<vector<int>>& res,vector<int>& cur,int k,int target,int index){
        if(target == 0&&k == 0){
            res.push_back(cur);
            return;
        }
        if(k == 0&&target!=0)
            return;
        for(int i = index;i <= 9;i++){
            cur.push_back(i);
            DFS(res,cur,k-1,target-i,i+1);
            cur.pop_back();
        }
    }
};
```
