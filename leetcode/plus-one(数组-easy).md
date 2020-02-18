```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    vector<int> plusOne(vector<int> &digits) {
        int n = digits.size();
        int temp = 1;
        for(int i=n-1;i>=0;i--){
            int num = digits[i];
            digits[i] = (num+temp)%10;
            temp = (num+temp)/10;
        }
        if(temp == 1){
            vector<int> res;
            res.push_back(1);
            for(int i = 1;i <= n;i++){
                res.push_back(digits[i-1]);
            }
            return res;
        }
        else
            return digits;
    }
};

int main()
{
    int n;
    while(cin >> n){
        vector<int> a;
        for(int i =0;i < n;i++){
            int temp;
            cin >> temp;
            a.push_back(temp);
        }
        Solution S;
        vector<int> b = S.plusOne(a);
        for(int i = 0; i < b.size();i++)
            cout << b[i];
    }
    return 0;
}



```
