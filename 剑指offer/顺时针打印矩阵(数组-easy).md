```cpp
class Solution {
public:
    vector<int> printMatrix(vector<vector<int> > matrix) {
        int m = matrix.size();
        int n = matrix[0].size();
        vector<int> res;
        if(m==0||n==0)
            return res;
        int t = 0,rowstart = 0,colstart = 0,rowend = m-1,colend = n-1;
        while(t < m*n){
            for(int i = colstart;i <= colend;i++){
                res.push_back(matrix[rowstart][i]);
                t++;
            }
            if(t>=m*n) break;
            rowstart++;
            
            for(int i = rowstart;i <= rowend;i++){
                res.push_back(matrix[i][colend]);
                t++;
            }
            if(t>=m*n) break;
            colend--;
            
            for(int i = colend;i >= colstart;i--){
                res.push_back(matrix[rowend][i]);
                t++;
            }
            if(t>=m*n) break;
            rowend--;
            
            for(int i = rowend;i >= rowstart;i--){
                res.push_back(matrix[i][colstart]);
                t++;
            }
            if(t>=m*n) break;
            colstart++;
        }
        return res;
    }
};

```
