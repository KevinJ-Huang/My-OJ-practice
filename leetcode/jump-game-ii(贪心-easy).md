```cpp

class Solution {
public:
    int jump(int A[], int n) {
        int res = 0,maxJump = 0,curJump = 0;
        for(int i = 0;i < n&&i<= maxJump;i++){
            if(i>curJump){
                res+=1;
                curJump = maxJump;
            }
            maxJump = max(maxJump,i+A[i]);
        }
        if(maxJump<n-1)
            return -1;
        else 
            return res;
    }
};


```
