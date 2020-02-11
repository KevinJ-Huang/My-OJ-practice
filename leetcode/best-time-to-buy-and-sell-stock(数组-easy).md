```cpp

#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    int maxProfit(vector<int> &prices) {
        int n = prices.size();
        int max_res = 0,min_res = prices[0];
        for(int i = 1;i < n;i++){
            if(prices[i]<min_res)
                min_res = prices[i];
            else
                max_res = max(max_res,prices[i]-min_res);
        }
        return max_res;
    }
};

int main()
{
    int n;
    while(cin>>n){
        vector<int> prices(n);
        for(int i = 0;i < n;i++)
            cin >> prices[i];
        Solution S;
        cout << S.maxProfit(prices) << endl;
    }
    return 0;
}

```
