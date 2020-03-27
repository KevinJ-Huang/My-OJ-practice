```cpp
class Solution {
public:
    int numDistinct(string S, string T) {
        int m = S.length();
        int n = T.length();
        vector<vector<int>> dp(n+1,vector<int>(m+1,0));
        for(int i = 0;i <= m;i++)
            dp[0][i] = 1;
        for(int i = 1;i < n+1;i++){
            for(int j = 1;j < m+1;j++){
                if(S[j-1] == T[i-1])
                    dp[i][j] = dp[i-1][j-1]+dp[i][j-1];
                else
                    dp[i][j] = dp[i][j-1];
            }
        }
        return dp[n][m];
    }
};


```
