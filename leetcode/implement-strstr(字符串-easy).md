```cpp
class Solution {
public:
    char *strStr(char *haystack, char *needle) {
        int m = strlen(haystack);
        int n = strlen(needle);
        if(m < n)
            return nullptr;
        for(int i = 0;i < m-n+1;i++){
            int j = 0;
            while(j<n){
                if(haystack[i+j]!=needle[j])
                    break;
                j++;
            }
            if(j==n)
                return haystack+i;
        }
        return nullptr;
    }
};


```
