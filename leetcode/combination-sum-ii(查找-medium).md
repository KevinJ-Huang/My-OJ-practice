```cpp
class Solution {
public:
    void trace(vector<vector<int>> &res,vector<int> &cur,vector<int> &num,int k,int target){
        if(target == 0){
            res.push_back(cur);
            return;
        }
        int n = num.size();
        if(target < 0||k >= n)
            return;
        for(int i = k;i < n;i++){
            if(i > k&&num[i] == num[i-1])
                continue;
            if(num[i] <= target){
                cur.push_back(num[i]);
                trace(res,cur,num,i+1,target-num[i]);
                cur.pop_back();
            }
        }
    }
    
    vector<vector<int> > combinationSum2(vector<int> &num, int target) {
        vector<vector<int> > res;
        vector<int> cur;
        sort(num.begin(),num.end());
        if(target < num[0])
            return res;
        trace(res,cur,num,0,target);
        return res;
    }
};


```
