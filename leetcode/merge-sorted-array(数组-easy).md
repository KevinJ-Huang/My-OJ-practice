```cpp
#include <iostream>

using namespace std;

class Solution {
public:
    void merge(int A[], int m, int B[], int n) {
        int i = m-1,j = n-1,t = m+n-1;
        while(i>=0&&j>=0){
            A[t--] = B[j]>A[i]?B[j--]:A[i--];
        }
        while(j>=0)
            A[t--] = B[j--];
    }
};

int main()
{
    int m,n;
    while(cin >> m >> n){
        int A[m+n+1],B[n];
        for(int i = 0;i < m;i++)
            cin >> A[i];
        for(int i = 0;i < n;i++)
            cin >> B[i];
        Solution S;
        S.merge(A,m,B,n);
    }
    return 0;
}

```
