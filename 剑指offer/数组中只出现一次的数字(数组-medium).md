```cpp
class Solution {
public:
    void FindNumsAppearOnce(vector<int> data,int* num1,int *num2) {
        int n = data.size();
        if(n < 2)
            return;
        int mxor = 0;
        int flag = 1;
        for(int i = 0;i < n;i++)
            mxor ^= data[i];
        while((mxor&flag)==0)
            flag <<= 1;
        *num1 = mxor;
        *num2 = mxor;
        for(int i = 0;i < n;i++){
            if((flag&data[i])==0)
                *num2 ^= data[i];
            else
                *num1 ^= data[i];
        }
    }
};

```
