```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    bool searchMatrix(vector<vector<int> > &matrix, int target) {
        int m = matrix.size(),n = matrix[0].size();
        int start = 0,stop = m*n-1;
        if(target < matrix[0][0] || target > matrix[m-1][n-1] || matrix.size() == 0 || matrix[0].size() == 0)
            return false;
        while(start <= stop){
            int mid = start+(stop-start)/2;
            int value = matrix[mid/n][mid%n];
            if (target > value) {
                start = mid + 1;
            } else if (target < value)
                stop = mid - 1;
            else
                return true;
         }
         return false;

    }
};

int main()
{
    int m,n,t;
    while(cin>>m>>n>>t){
        Solution S;
        vector<vector<int>> matrix(m);
        for(int i = 0;i < m;i++)
            matrix[i].resize(n);
        for(int i = 0;i < m;i++){
            for(int j = 0;j < n;j++){
                int temp;
                cin >> temp;
                matrix[i][j] = temp;
            }
        }
        cout << S.searchMatrix(matrix,t) << endl;
    }
    return 0;
}

```
