```cpp
class Solution {
public:
    vector<vector<string>> partition(string s) {
        vector<vector<string>> res;
        vector<string> cur;
        dfs(s,0,cur,res);
        return res;
    }
    void dfs(string s,int start,vector<string>& cur,vector<vector<string>>& res){
        if(start == s.size()){
            res.push_back(cur);
            return;
        }
        for(int i = start;i < s.size();i++){
            if(!isSym(s,start,i))
                 continue;
            cur.push_back(s.substr(start,i-start+1));
            dfs(s,i+1,cur,res);
            cur.pop_back();
        }
    }
    bool isSym(string s,int start,int last){
        while(start < last){
            if(s[start]!=s[last])
                return false;
            start++;
            last--;
        }
        return true;
    }
};

```
