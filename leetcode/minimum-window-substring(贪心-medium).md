```cpp
class Solution {
public:
    string minWindow(string S, string T) {
        int n = S.size();
        int k = T.size();
        string res = "";
        if(n < k)
            return res;
        unordered_map<char,int> m;
        int MinL = INT_MAX;
        for(char c:T)
            m[c]++;
        int cnt = 0,left = 0;
        for(int i = 0;i < n;i++){
            if(--m[S[i]]>=0)
               cnt++;
            while(cnt == k){
                if(MinL > i-left+1){
                    MinL = i-left+1;
                    res = S.substr(left,MinL);
                }
                if(++m[S[left]] > 0)
                    --cnt;
                left++;
            }
        }
        return res;
    }
};


```
