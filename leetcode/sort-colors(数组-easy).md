```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    void sortColors(int A[], int n) {
        int before = 0, after = n-1;
        for(int i = 0;i < n;i++){
            while(i<after&&A[i] == 2){swap(A[i],A[after--]);}
            while(i>before&&A[i] == 0){swap(A[i],A[before++]);}
        }
    }
};

int main()
{
    int n;
    while(cin >> n){
        int a[n];
        for(int i = 0;i < n;i++)
            cin >> a[i];
        Solution S;
        S.sortColors(a,n);
    }
    return 0;
}

```
