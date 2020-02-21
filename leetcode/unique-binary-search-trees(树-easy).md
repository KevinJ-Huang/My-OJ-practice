```cpp
class Solution {
public:
    int numTrees(int n) {
        if(n <= 1)
            return 1;
        else if(n > 1){
            int cnt = 0;
            for(int i = 1;i<=n;i++){
                cnt = cnt+numTrees(i-1)*numTrees(n-i);
            }
            return cnt;
        }
    }
};

```
