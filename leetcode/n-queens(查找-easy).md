```cpp

class Solution {
public:
    int x[20];
    bool isplace(int t){
        for(int i = 1;i < t;i++){
            if(x[i] == x[t]||abs(x[i]-x[t])==abs(i-t))
                return false;
        }
        return true;
    }

    void traceback(int t,vector<vector<string> > &res,vector<string> cur,int n){
        if(t > n){
            res.push_back(cur);
            return ;
        }
        else{
            for(int i = 1;i <= n;i++){
                x[t] = i;
                if(isplace(t)){
                     cur[t-1][i-1] = 'Q';
                     traceback(t+1,res,cur,n);
                     cur[t-1][i-1] = '.';
                }
            }
        }
    }

    vector<vector<string> > solveNQueens(int n) {
        vector<vector<string>> res;
        vector<string> cur(n,string(n,'.'));
        traceback(1,res,cur,n);
        return res;
    }
};





```
