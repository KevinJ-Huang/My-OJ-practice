```cpp
class Solution {
public:
    bool isMatch(const char *s, const char *p) {
        int i = 0;
        int j = 0;
        int indexmatch = 0;
        int indexstart = -1;
        while(s[i]!='\0'){
            if(p[j] == s[i]||p[j] == '?'){
                i++;
                j++;
            }
            else if(p[j]!='\0'&&p[j] == '*'){
                indexmatch = i;
                indexstart = j;
                j++;
            }
            else if(indexstart!=-1){
                indexmatch++;
                i = indexmatch;
                j = indexstart+1;
            }
            else
                return false;
        }
        while(p[j]!='\0'&&p[j]=='*')
            j++;
        return p[j] == '\0';
    }
};


```
