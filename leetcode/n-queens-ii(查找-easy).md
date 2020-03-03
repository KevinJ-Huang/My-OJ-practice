```cpp
class Solution {
public:
    int x[20];
    int cnt = 0;
    int totalNQueens(int n) {
        backtrace(1,n);
        return cnt;
    }
    bool isplace(int t){
        for(int i = 1;i < t;i++){
            if(abs(x[t]-x[i])==abs(t-i)||x[t]==x[i])
                return false;
        }
        return true;
    }

    void backtrace(int t,int n){
        if(t > n)
            cnt++;
        else{
            for(int i = 1;i <= n;i++){
                x[t] = i;
                if(isplace(t))
                    backtrace(t+1,n);
            }
        }
    }
};

```
