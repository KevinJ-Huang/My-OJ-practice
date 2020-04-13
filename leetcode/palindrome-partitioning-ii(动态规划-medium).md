```cpp
class Solution {
public:
    int minCut(string s) {
        int n = s.size();
        vector<int> dp(n);
        vector<vector<bool>> cur(n,vector<bool>(n));
        for(int i = 0;i < n;i++){
            dp[i] = i;
            for(int j = 0;j <= i;j++){
                if(s[i] == s[j]&&(i-j<2||cur[j+1][i-1])){
                    cur[j][i] = true;
                    dp[i] = (j==0)?0:min(dp[i],dp[j-1]+1);
                }
            }
        }
        return dp[n-1];
    }
};

```
