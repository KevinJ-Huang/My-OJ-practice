```cpp

class Solution {
public:
    int firstMissingPositive(int A[], int n) {
        int MinN = INT_MAX;
        for(int i = 0;i < n;i++){
            int num = A[i];
            while(num>0 && num<=n && A[num-1]!=num)
                swap(num,A[num-1]);
        }
        for(int i = 0;i < n;i++){
            if(A[i] != i+1)
                return i+1;
        }
        return n+1;
    }
};



```
