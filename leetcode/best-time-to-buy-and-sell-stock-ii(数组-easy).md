```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    int maxProfit(vector<int> &prices) {
        int res = 0, n = prices.size();
        for(int i = 0;i < n-1;i++){
            if(prices[i+1]>prices[i])
                res += (prices[i+1]-prices[i]);
        }
        return res;
    };
};

int main()
{
    int n;
    while(cin >> n){
        vector<int> prices;
        for(int i = 0;i < n;i++){
            int temp;
            cin >> temp;
            prices.push_back(temp);
        }
        Solution S;
        cout << S.maxProfit(prices) << endl;
    }
    return 0;
}

```
