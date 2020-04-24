```cpp
class Solution {
public:
    int atoi(const char *str) {
        if(*str=='\0') return 0;
        const char* p = str;
        while(*p ==' ') ++p;
        int flag = 1,res = 0;
        if(*p=='-') flag = -1;
        if(*p=='-'||*p=='+') p++;
        while(*p>='0'&&*p<='9'){
            int cur = res*10+(*p-'0');
            if(cur/10!=res)
                return flag>0?INT_MAX:INT_MIN;
            res = cur;
            p++;
        }
        return res*flag;
    }
};

```
