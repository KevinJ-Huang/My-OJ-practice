```cpp
class Solution {
public:
    string removeKdigits(string num, int k) {
        int n = num.size();
        if(k >= n)
            return "0";
        else{
            string res;
            for(int i = 0;i < n;i++){
                while(res.size()&&res.back()>num[i]&&k){
                    k--;
                    res.pop_back();
                }
                if(res.size()==0&&num[i]=='0')
                    continue;
                res+=num[i];
            }
            while(k > 0&&!res.empty()){
                res.pop_back();
                k--;
            }
            return res==""?"0":res;
        }
    }
};
```
