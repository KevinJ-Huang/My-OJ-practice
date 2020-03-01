```cpp
class Solution {
public:
    bool canJump(int A[], int n) {
        int MaxJump = 0;
        for(int i = 0;i < n&&i<=MaxJump;i++){
            MaxJump = max(MaxJump,i+A[i]);
        }
        if(MaxJump<n-1)
            return false;
        return true;
    }
};


```
