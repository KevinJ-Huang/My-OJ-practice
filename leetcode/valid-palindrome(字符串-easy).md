```cpp
class Solution {
public:
    bool isPalindrome(string s) {
        int n = s.size();
        int left = 0,right = n-1;
        while(left < right){
            if(!isValidStr(s[left])) left++;
            else if(!isValidStr(s[right])) right--;
            else if((s[left]+32-'a')%32!=(s[right]+32-'a')%32)
                return false;
            else{
                left++;
                right--;
            }
        }
        return true;
    }
    bool isValidStr(char &s){
        if(s>='a'&&s<='z')
              return true;
        if(s>='A'&&s<='Z')
              return true;
        if(s>='0'&&s<='9')
              return true;
        return false;
    }
    
};



```
