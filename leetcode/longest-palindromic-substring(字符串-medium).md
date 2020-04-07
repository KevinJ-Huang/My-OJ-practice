```cpp
class Solution {
public:
    string longestPalindrome(string s) {
        int n = s.size();
        if(n < 2)
            return s;
        int res = 0,start = 0;
        for(int i = 0;i < n;){
            if(n-i<=res/2)
                break;
            int left = i,right = i;
            while(right<n-1&&s[right+1]==s[right])
                ++right;
            i = right+1;
            while(right < n-1&&left>0&&s[right+1]==s[left-1]){
                ++right;
                --left;
            }
            if(res < right-left+1){
                res = right-left+1;
                start = left;
            }
        }
        return s.substr(start,res);
    }
};


```
