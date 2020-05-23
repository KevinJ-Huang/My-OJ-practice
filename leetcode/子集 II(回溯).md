```cpp
class Solution {
public:
    vector<vector<int>> subsetsWithDup(vector<int>& nums) {
        int n = nums.size();
        vector<vector<int>> res;
        vector<int> cur;
        sort(nums.begin(),nums.end());
        DFS(res,cur,nums,0);
        return res;
    }
    void DFS(vector<vector<int>>& res,vector<int>& cur,vector<int>& nums,int index){
        res.push_back(cur);
        if(index >= nums.size())
            return;
        unordered_map<int,int> mp;
        for(int i = index;i < nums.size();i++){
            if(mp.count(nums[i])==1)
                continue;
            cur.push_back(nums[i]);
            DFS(res,cur,nums,i+1);
            cur.pop_back();
            mp[nums[i]] = 1;
        }
    }
};
```
