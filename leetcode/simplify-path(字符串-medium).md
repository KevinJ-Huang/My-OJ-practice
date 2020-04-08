```cpp
class Solution {
public:
    string simplifyPath(string path) {
        vector<string> res;
        int n = path.size(),i = 0;
        while(i < n){
            while(path[i] == '/'&&i < path.size())
                ++i;
            if(i == path.size())
                break;
            int start = i;
            while(path[i] != '/'&&i < path.size())
                ++i;
            int last = i-1;
            string s = path.substr(start,last-start+1);
            if(s ==  ".."){
                if(!res.empty())
                    res.pop_back();
            }
            else if(s != "."){
                res.push_back(s);
            }
        }
        if(res.empty())
            return "/";
        string out;
        int m = res.size();
        for(int i = 0;i < m;i++)
            out += '/'+res[i];
        return out;
    }
};

```
