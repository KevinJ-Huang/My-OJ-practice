#### 输入一个递增排序的数组和一个数字S，在数组中查找两个数，使得他们的和正好是S，如果有多对数字的和等于S，输出两个数的乘积最小的。
思路：没什么好说的，因为是排好序的，所以从前到后和从后到前遍历夹逼即可，第一对相加为S的数就满足乘积最小。
```cpp
#include <iostream>

using namespace std;

class Solution {
public:
    vector<int> FindNumbersWithSum(vector<int> array,int sum) {
        vector<int> res;
        int n = array.size();
        for(int i=0,j=n-1;i < j;){
            if(array[i]+array[j]==sum){
                res.push_back(array[i]);
                res.push_back(array[j]);
                break;
            }
            if(array[i]+array[j]<sum)
                i++;
            else
                j--;
        }
        return res;
    }
};
```
