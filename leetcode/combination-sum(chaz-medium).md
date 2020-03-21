```cpp

class Solution {
public:
    void trace(vector<vector<int> > &res,vector<int> cur,vector<int> &candidates,int k,int target){
        if(target == 0){
            res.push_back(cur);
            return;
        }
        if(target<0||k>=candidates.size())
            return;
        cur.push_back(candidates[k]);
        trace(res,cur,candidates,k,target-candidates[k]);
        cur.pop_back();
        trace(res,cur,candidates,k+1,target);
    }
    vector<vector<int> > combinationSum(vector<int> &candidates, int target) {
        vector<vector<int> > res;
        vector<int> cur;
        sort(candidates.begin(), candidates.end());
        if(target < candidates[0])
            return res;
        trace(res,cur,candidates,0,target);
        return res;
    }
};



```
