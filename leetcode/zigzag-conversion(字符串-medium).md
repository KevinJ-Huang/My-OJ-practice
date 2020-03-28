```cpp
class Solution {
public:
    string convert(string s, int nRows) {
        if(s.size()==0||nRows<=0)
            return "";
        if(nRows == 1)
            return s;
        string res = "";
        int gap = 2*(nRows-1);
        for(int i = 0;i < nRows;i++){
            for(int j = i;j < s.length();j+=gap){
                res+=s[j];
                int t = j+gap-2*i;
                if(i>0 && i<nRows-1 && t<s.size())
                    res+=s[t];
            }
        }
        return res;
    }
};



```
