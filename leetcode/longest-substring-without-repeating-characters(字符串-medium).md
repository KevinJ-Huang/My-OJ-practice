```cpp
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        int n = s.size();
        int res = 0;
        if(n <= 1)
            return n;
        unordered_map<int,int> m;
        int left = -1;
        for(int i = 0;i < s.size();i++){
            if(m.count(s[i])&&m[s[i]] > left)
                 left = m[s[i]]; 
            m[s[i]] = i;
            res = max(res,i-left);
        }
        return res;
    }
};



```
