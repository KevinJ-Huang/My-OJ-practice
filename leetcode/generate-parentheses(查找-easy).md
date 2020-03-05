```cpp

class Solution {
public:
    int n;
    void Addsym(vector<string> &res,int left,int right,string s){
        if(left==n&&right==n){
            res.push_back(s);
            return;
        }
        if(left < n){
            Addsym(res,left+1,right,s+"(");
        }
        if(left>right&&right<n){
            Addsym(res,left,right+1,s+")");
        }

    }

    vector<string> generateParenthesis(int n){
        this->n = n;
        vector<string> res;
        Addsym(res,0,0,"");
        return res;
    }
};


```
