```cpp
class Solution {
public:
    bool wordBreak(string s, unordered_set<string> &dict) {
        int m = s.size();
        int n = dict.size();
        vector<bool> dp(m+1);
        dp[0] = true;
        for(int i = 0;i < m+1;i++){
            for(int j = 0;j < i;j++){
                if(dp[j]&&dict.count(s.substr(j,i-j))){
                    dp[i] = true;
                    break;
                }
            }
        }
        return dp[m];
    }
};




```
