```cpp
class Solution {
public://以p为主对象分情况讨论
    bool isMatch(const char *s, const char *p) {
        //int n1 = strlen(s), n2 = strlen(p);
        if(*p == '\0') return *s == '\0';
        if(strlen(p) == 1)return (strlen(s) == 1 && (s[0] == p[0] || p[0] == '.'));
        if(p[1] != '*'){
            if(*s == '\0') return 0;
            return (s[0] == p[0] || p[0] == '.') && isMatch(s + 1, p + 1);
        }
        //以下是 p[1] == '*'的情况
        while(*s != '\0' && (s[0] == p[0] || p[0] == '.')){//首元素匹配的情况
            if(isMatch(s, p + 2)) return 1;//先删去p的前两个元素检验（情况1）
            s = s + 1; //删去s首元素检验（情况2）
        }
        //首元素不匹配 和 s为空字符串 的情况 （此时s的首元素可能是后面的）
        return isMatch(s, p + 2);
    }
};

```
