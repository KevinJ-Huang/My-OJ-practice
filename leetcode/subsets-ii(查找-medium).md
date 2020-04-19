```cpp
class Solution {
public:
    vector<vector<int> > subsetsWithDup(vector<int> &S) {
        vector<vector<int> > res;
        vector<int> cur;
        sort(S.begin(),S.end());
        DFS(S,0,cur,res);
        return res;
    }
    void DFS(vector<int> &S,int index,vector<int> &cur,vector<vector<int>> &res){
        res.push_back(cur);
        for(int i = index;i < S.size();i++){
            if(i > index&&S[i] == S[i-1])
                 continue;
            cur.push_back(S[i]);
            DFS(S,i+1,cur,res);
            cur.pop_back();
        }
    }
};

```
