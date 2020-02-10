```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    int maxArea(vector<int> &height) {
        int i = 0, j = height.size()-1;
        int Amax = 0;
        while(i < j){
            Amax = max(Amax,(j-i)*min(height[i],height[j]));
            height[i] < height[j]?++i:--j;
        }
        return Amax;
    }
};

int main()
{
    int n;
    while(cin>>n){
        vector<int> height(n);
        for(int i = 0;i < n;i++){
            cin >> height[i];
        }
        Solution S;
        cout << S.maxArea(height) << endl;
    }
    return 0;
}


```
