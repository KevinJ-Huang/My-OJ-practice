```cpp
class Solution {
public:
    vector<vector<int> > subsets(vector<int> &S) {
        vector<vector<int>> res;
        vector<int> cur;
        sort(S.begin(),S.end());
        int m = S.size();
        for(int i = 0;i <= m;i++){
            DFS(S,0,i,cur,res);
        }
        return res;
    }
    void DFS(vector<int> &S,int start,int len,vector<int> &cur,vector<vector<int>> &res){
        if(len < 0)  return;
        else if(len == 0) res.push_back(cur);
        else{
            for(int i = start;i < S.size();i++){
                cur.push_back(S[i]);
                DFS(S,i+1,len-1,cur,res);
                cur.pop_back();
            }
        }
    }
};

```
