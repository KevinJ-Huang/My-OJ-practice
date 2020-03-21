```cpp
class Solution {
public:
    void solveSudoku(vector<vector<char> > &board) {
        if(board.empty()||board.size()==0||board[0].size()==0)
            return;
        solve(board,0);
    }
    bool solve(vector<vector<char> > &board,int num){
        if(num == 81)
            return true;
        int x = num/9;
        int y = num%9;
        if(board[x][y]!='.'){
            if(solve(board,num+1))
                return true;
            return false;
        }
        for(char c = '1';c <='9';c++){
            if(!isValid(board,x,y,c))
                continue;
            board[x][y] = c;
            if(solve(board,num+1))
                return true;
            board[x][y] = '.';
        }
        return false;
    }
    
    bool isValid(vector<vector<char> > &board,int x,int y,char c){
         for(int i = 0;i < board.size();i++){
              if(board[x][i] == c)
                   return false;
         }
         for(int i = 0;i < board[0].size();i++){
              if(board[i][y] == c)
                   return false;
         }
         for(int i = 0;i < 3;i++){
             for(int j = 0;j < 3;j++){
                 if(board[x/3*3+i][y/3*3+j] == c)
                     return false;
             }
         }
         return true;
    }
};



```
