```cpp
class Solution {
public:
    int lengthOfLastWord(const char *s) {
        int n = strlen(s);
        int res = 0;
        if(n==0)
            return res;
        for(int i = n-1;i >= 0;i--){
            if(s[i] == ' '&&res > 0){
                break;
            }
            if(s[i] == ' ')
                continue;
            res++;
        }
        return res;
    }
};


```
