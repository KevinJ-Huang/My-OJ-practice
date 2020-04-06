```cpp
class Solution {
public:
    vector<int> findSubstring(string S, vector<string> &L) {
        if(S.empty()||L.empty())
            return {};
        vector<int> res;
        int n = L.size(), len = L[0].size();
        unordered_map<string,int> wordCnt;
        for(auto &l:L)
            ++wordCnt[l];
        for(int i = 0;i <= (int)S.size()-n*len;i++){
            unordered_map<string,int> strCnt;
            int j = 0;
            for(j = 0;j < n;j++){
                string t = S.substr(i+j*len,len);
                if(!wordCnt.count(t))
                    break;
                ++strCnt[t];
                if(strCnt[t]>wordCnt[t])
                    break;
            }
            if(j==n)
                 res.push_back(i);
        }
        return res;
    }
};


```
