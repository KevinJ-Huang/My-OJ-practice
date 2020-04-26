```cpp
class Solution {
public:
    int NumberOf1Between1AndN_Solution(int n)
    {
        if(n<=0)
            return 0;
        int res = 0,d = 0,f = 0;
        for(long i = 1;i <= n;i *= 10){
            long cur = i*10;
            int d = (n/cur)*i;
            if(n%cur>i*2-1)
               f = i;
            else if(n%cur<i)
               f = 0;
            else
               f = n%cur-i+1;
            res+=(f+d);
        }
        return res;
    }
};


```
