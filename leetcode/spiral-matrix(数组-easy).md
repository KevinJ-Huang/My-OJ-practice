```cpp
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int> > &matrix) {
        vector<int> res;
        int m = matrix.size();
        int n = matrix[0].size();
        if(m==0||n==0)
            return res;
        int cnt = 0, rowstart = 0, rowend = m-1, colstart = 0, colend = n-1;;
        while(true){
            for(int i = colstart;i<=colend;i++){
                res.push_back(matrix[rowstart][i]);
                cnt++;
            }
            if(cnt >= m*n)
                break;
            for(int i = rowstart+1;i<=rowend;i++){
                res.push_back(matrix[i][colend]);
                cnt++;
            }
            if(cnt >= m*n)
                break;
            for(int i = colend-1;i>=colstart;i--){
                res.push_back(matrix[rowend][i]);
                cnt++;
            }
            if(cnt >= m*n)
                break;
            for(int i = rowend-1;i>rowstart;i--){
                res.push_back(matrix[i][colstart]);
                cnt++;
            }
            if(cnt >= m*n)
                break;
            rowstart++;
            rowend--;
            colstart++;
            colend--;
        }
        return res;
    }
};


```
