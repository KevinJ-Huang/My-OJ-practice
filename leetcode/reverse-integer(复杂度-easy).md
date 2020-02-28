```cpp

class Solution {
public:
    int reverse(int x) {
        int res = 0;
        while(x!=0){
           int tail = x%10;
           int cur = res*10+tail;
           if((cur-tail)/10!=res)
               return 0;
           res = cur;
           x = x/10;
        }
        return res;
    }
};

```
