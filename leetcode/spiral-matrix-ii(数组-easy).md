```cpp

#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    vector<vector<int> > generateMatrix(int n) {
        vector<vector<int>> matrix(n,vector<int>(n));
        int cnt = 1, rowstart = 0, rowend = n-1, colstart = 0, colend = n-1;
        while(cnt <= n*n){
            for(int i = colstart;i <= colend;i++)
                 matrix[rowstart][i] = cnt++;
            for(int i = rowstart+1;i <= rowend;i++)
                 matrix[i][colend] = cnt++;
            for(int i = colend-1;i >= colstart;i--)
                 matrix[rowend][i] = cnt++;
            for(int i = rowend-1;i > rowstart;i--)
                 matrix[i][colstart] = cnt++;
            rowstart++;
            rowend--;
            colstart++;
            colend--;
        }
        return matrix;

    }
};

int main()
{
    int n;
    while(cin >> n){
        Solution S;
        vector<vector<int> > matrix = S.generateMatrix(n);
        for(int i = 0;i < n;i++){
            for(int j = 0;j < n;j++){
                cout << matrix[i][j] << " ";
           }
           cout << endl;
        }
    }

    return 0;
}



```
