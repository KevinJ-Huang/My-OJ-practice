```cpp
#include <iostream>
#include <vector>
using namespace std;


int main()
{
    int n,m;
    while(cin >> n >> m){
        vector<int> a;
        a.push_back(0);
        for(int i =  0;i < n;i++){
            int t;
            cin >> t;
            a.push_back(t);
        }
        vector<vector<long>> dp(n+1,vector<long>(m+1,0));
        for(int i = 0;i <= n;i++)
            dp[i][0] = 1;

        for(int i = 1;i <= n;i++){
            for(int j = 1;j <= m;j++){
                if(j>=a[i])
                    dp[i][j] = dp[i-1][j]+dp[i-1][j-a[i]];
                else
                    dp[i][j] = dp[i-1][j];
            }
        }
        cout << dp[n][m] << endl;
    }
    return 0;
}
```
