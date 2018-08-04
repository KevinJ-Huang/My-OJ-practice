#### 输入n个整数，找出其中最小的K个数。例如输入4,5,1,6,2,7,3,8这8个数字，则最小的4个数字是1,2,3,4,。
思路：可以建一个堆解决，这里长时间不写那个已经不会写了，直接来个排序了。。
```cpp
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

class Solution {
public:
    vector<int> GetLeastNumbers_Solution(vector<int> input, int k) {
       vector<int> res;
       if(input.size()<k)
           return res;
       sort(input.begin(),input.end());
       for(int i=0;i<k;i++)
           res.push_back(input[i]);
       return res;
    }
};

int main()
{
    int a[10]={1,2,3,4,5,6,7,8,9,10};
    vector<int>input(a,a+10);
    Solution S;
    vector<int>out = S.GetLeastNumbers_Solution(input,6);
    for(int i=0;i<6;i++)
         cout << out[i] << endl;
    return 0;
}

```
