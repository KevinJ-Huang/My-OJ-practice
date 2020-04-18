```cpp
class Solution {
public:
    void solve(vector<vector<char>> &board) {
        int m = board.size();
        int n = board[0].size();
        for(int i = 0;i < m;i++){
            for(int j = 0;j < n;j++){
                if((i==0||i==m-1||j==0||j==n-1)&&board[i][j]=='O')
                    DFS(board,i,j);
            }
        }
        for(int i =0;i < m;i++){
            for(int j = 0;j < n;j++){
                if(board[i][j] == 'O') board[i][j] = 'X';
                if(board[i][j] == 'S') board[i][j] = 'O';
            }
        }
    }
    void DFS(vector<vector<char>> &board,int i,int j){
        if(board[i][j] == 'O'){
            int m = board.size();
            int n = board[0].size();
            board[i][j] = 'S';
            if(i > 0&&board[i-1][j]=='O')
                DFS(board,i-1,j);
            if(i < m-1&&board[i+1][j]=='O')
                DFS(board,i+1,j);
            if(j < n-1&&board[i][j+1]=='O')
                DFS(board,i,j+1);
             if(j > 0&&board[i][j-1]=='O')
                DFS(board,i,j-1);
        }
    }
};




```
