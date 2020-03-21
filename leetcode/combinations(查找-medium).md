```cpp
class Solution {
public:  
    void trace(int num,int n,int k,vector<vector<int> > &res,vector<int> cur){
         if(k == 0){
             res.push_back(cur);
             return;
         }
         if(num > n)
             return;
         cur.push_back(num);
         trace(num+1,n,k-1,res,cur);
         cur.pop_back();
         trace(num+1,n,k,res,cur);
    }
    
    vector<vector<int> > combine(int n, int k) {
        vector<vector<int> > res;
        vector<int> cur;
        trace(1,n,k,res,cur);
        return res;
    }
};



```
