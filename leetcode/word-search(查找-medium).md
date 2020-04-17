```cpp
class Solution {
public:
    bool exist(vector<vector<char> > &board, string word) {
        int m = board.size(),n = board[0].size();
        if(m == 0||n == 0)
               return false;
        vector<vector<bool> > visited(m,vector<bool>(n));
        for(int i = 0;i < m;i++){
            for(int j = 0;j < n;j++){
                if(trace(board,word,0,i,j,visited))
                    return true;
            }
        }
        return false;
    }
    bool trace(vector<vector<char> > &board,string word,int idx,int i,int j,vector<vector<bool> > &visited){
        if(idx == word.size())
              return true;
        int m = board.size(),n = board[0].size();
        if(i <0||j < 0||i >=m||j>=n||visited[i][j]||board[i][j]!=word[idx]) return false;
        visited[i][j] = true;
        bool res = (trace(board,word,idx+1,i-1,j,visited)||
        trace(board,word,idx+1,i+1,j,visited)||trace(board,word,idx+1,i,j-1,visited)||
        trace(board,word,idx+1,i,j+1,visited));
        visited[i][j] = false;
        return res;
    }
};



```
