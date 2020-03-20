```cpp

class Solution {
public:
    vector<string> letterCombinations(string digits) {
        vector<string> res = {""};
        unordered_map<char,string> mp = {{'2',"abc"},{'3',"def"},{'4',"ghi"},{'5',"jkl"},
        {'6',"mno"},{'7',"pqrs"},{'8',"tuv"},{'9',"wxyz"}};
        for(auto c:digits){
            int sz = res.size();
            for(int i =0;i<sz;i++)
                for(auto t:mp[c])
                    res.push_back(res[i]+t);
            res.erase(res.begin(),res.begin()+sz);
        }
        return res;
    }
};


```
