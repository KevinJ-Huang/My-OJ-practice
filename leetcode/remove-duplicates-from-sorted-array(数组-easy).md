```cpp
#include <iostream>

using namespace std;


class Solution {
public:
    int removeDuplicates(int A[], int n) {
        int cnt = 0;
        for(int i = 0;i < n;i++){
            if(A[i] == A[i+1]&&i+1<n)
                continue;
            else
               A[cnt++] = A[i];
        }
        return cnt;
    }
};

int main()
{
    int n;
    while(cin>>n){
        int A[n];
        for(int i = 0;i < n;i++)
            cin >> A[i];
        Solution S;
        cout << S.removeDuplicates(A,n) << endl;
    }
    return 0;
}

```
