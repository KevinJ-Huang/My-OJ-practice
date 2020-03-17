```cpp
class Solution {
public:
    double pow(double x, int n) {
        if(n == 0)
            return 1;
        if(n < 0)
            return 1/x*pow(1/x,-(n+1));
        if(n%2 == 0)
            return pow(x*x,n/2);
        else 
            return pow(x*x,n/2)*x;
        
    }
};



```
