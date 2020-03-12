```cpp


class Solution {
public:
    int divide(int dividend, int divisor) {
        if(dividend == 0||divisor == 0) 
             return 0;
        long long a = abs((long long)dividend);
        long long b = abs((long long)divisor);
        int res = 0;
        while(a>=b){
            int cnt = 1;
            long sum = b;
            while(sum+sum<=a){
                sum+=sum;
                cnt+=cnt;
            }
            res+=cnt;
            a-=sum;
        }
        if((dividend<0)^(divisor<0))
            res=-res;
        return res;
    }
};


```
