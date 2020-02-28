```cpp

class Solution {
public:
    string longestCommonPrefix(vector<string> &strs) {
        int length = strs.size();
        if(length==0)
             return "";
        sort(strs.begin(),strs.end());
        int n = min(strs[0].size(),strs[length-1].size());
        int i = 0;
        while(i<n){
            if(strs[0][i]!=strs[length-1][i])
                 return strs[0].substr(0,i);
            i++;
        }
        return strs[0].substr(0,n);      
    }
};

```
