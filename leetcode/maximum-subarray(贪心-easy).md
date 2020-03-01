```cpp

class Solution {
public:
    int maxSubArray(int A[], int n) {
       int res = 0, Maxsum = A[0];
       for(int i = 0;i < n;i++){
           if(res < 0)
               res = 0;
           res+=A[i];
           Maxsum = max(Maxsum,res);
       }
       return Maxsum; 
    }
};


```
