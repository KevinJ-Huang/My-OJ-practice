```cpp

class Solution {
public:
    void nextPermutation(vector<int> &num) {
        int i = num.size()-1, j = num.size()-1;
        if(i<=0)
             return;
        while(i > 0 && num[i] <= num[i-1])
            i--;
        if (i==0)
            reverse(num.begin(),num.end());
        else{
            while(num[j] <= num[i-1])
                j--;
            swap(num[i-1],num[j]);
            sort(num.begin()+i,num.end());
        }
    }
};



```
