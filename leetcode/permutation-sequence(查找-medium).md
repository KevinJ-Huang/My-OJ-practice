```cpp

class Solution {
public:
    string getPermutation(int n, int k) {
        string res;
        vector<int> f(n,1);
        vector<char> num(n,1);
        
        for(int i = 1;i < n;i++)
            f[i] = f[i-1]*i;
        for(int i = 0;i < n;i++)
            num[i] = '0'+(i+1);
        k--;
        for(int i = n;i >=1;i--){
            int t = k/f[i-1];
            k = k%f[i-1];
            res.push_back(num[t]);
            num.erase(num.begin()+t);
        }
        return res;
    }
    
};



```
