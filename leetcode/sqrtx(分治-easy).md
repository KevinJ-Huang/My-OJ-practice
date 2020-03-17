```cpp
class Solution {
public:
    int sqrt(int x) {
        if(x == 0||x == 1)
            return x;
        long res = x;
        while(res > x/res){
            res = (res+x/res)/2;
        }
        return (int)res;
    }
};



```


































