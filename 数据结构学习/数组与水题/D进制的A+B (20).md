#### 输入两个非负10进制整数A和B(<=230-1)，输出A+B的D (1 < D <= 10)进制数。
水题，用字符串模拟

```cpp
#include <iostream>
#include <string>

using namespace std;


class Solution{
public:
    string Transfer(int num,int d){
        string res="";
        while(num > 0){
            res =char(num%d+'0')+res;
            num = num/d;
        }
        return res;
    }
};

int main()
{
    int a,b,d;
    Solution S;
    cin >> a >> b >> d;
    cout << S.Transfer(a+b,d) << endl;
    return 0;
}

```
