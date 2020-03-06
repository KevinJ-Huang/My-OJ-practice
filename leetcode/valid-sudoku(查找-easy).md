```cpp
class Solution {
public:
    bool isValidSudoku(vector<vector<char> > &board) {
        int m = board.size();
        int n = board[0].size();
        bool row[9][9] = {false},col[9][9] = {false}, nine[9][9]={false};
        for(int i = 0;i < m;i++){
            for(int j = 0;j < n;j++){
                if(board[i][j]!='.'){
                    int num = board[i][j] - '1';
                    int k = i/3*3+j/3;
                    if(row[i][num]||col[j][num]||nine[k][num])
                        return false;
                    row[i][num] = col[j][num] = nine[k][num] = true;
                }
            }
        }
        return true;
    }
};

```
