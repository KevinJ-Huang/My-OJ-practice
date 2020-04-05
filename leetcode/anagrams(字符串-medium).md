```cpp
class Solution {
public:
    vector<string> anagrams(vector<string> &strs) {
        vector<string> res;
        unordered_map<string,int> mp;
        int n = strs.size();
        if(n<=0)
            return res;
        for(int i = 0;i < n;i++){
            string t = strs[i];
            sort(t.begin(),t.end());
            mp[t]++;
        }
        for(int i = 0;i < n;i++){
            string t = strs[i];
            sort(t.begin(),t.end());
            if(mp[t]>1)
                res.push_back(strs[i]);
        }
        return res;
    }
};




```
