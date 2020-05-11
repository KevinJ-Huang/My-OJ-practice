```cpp
class Solution {
public:
    int largestSumAfterKNegations(vector<int>& A, int K) {
        int n = A.size();
        if(n < 1)
            return 0;
        sort(A.begin(),A.end());
        int res = 0;
        int flag;
        if(A[0] <= 0)
            flag = 0;
        else
            flag = 1;
        if(flag == 1){
            A[0] = -A[0];
            K = 0;
        }
        for(int i = 0;i < n;i++){
            if(flag == 0&&A[i] > 0&&K > 0&&K%2==0){
                K = 0;
            }
            if(flag == 0&&A[i] > 0&&K > 0&&K%2==1){
                K = 0;
                if(A[i] > A[i-1])
                    A[i-1] = -A[i-1];
                else
                    A[i] = -A[i]; 
            }
            if(A[i] < 0&&K > 0){
                A[i] = -A[i];
                K--;
            }
        }
        for(int i = 0;i < n;i++){
            res+=A[i];
        }
        return res;
    }
};

```
