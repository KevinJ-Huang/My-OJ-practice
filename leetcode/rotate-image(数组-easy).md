```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    void rotate(vector<vector<int> > &matrix) {
        int n = matrix.size();
        for(int i =0;i < n;i++){
            for(int j = 0;j < n-i;j++){
                swap(matrix[i][j],matrix[n-1-j][n-1-i]);
            }
        }
        for(int i =0;i < n/2;i++){
            for(int j = 0;j < n;j++){
                swap(matrix[i][j],matrix[n-i-1][j]);
            }
        }
    }
};

int main()
{
    int n;
    while(cin >> n){
        vector<vector<int>> matrix(n);
        for(int i = 0;i < n;i++)
            matrix[i].resize(n);
        for(int i = 0;i < n;i++){
            for(int j = 0;j < n;i++){
                int temp;
                cin >> temp;
                matrix[i][j] = temp;
            }
        }
        Solution S;
        S.rotate(matrix);
    }
    return 0;
}

```
