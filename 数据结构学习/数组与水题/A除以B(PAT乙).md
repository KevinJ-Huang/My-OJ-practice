#### 本题要求计算A/B，其中A是不超过1000位的正整数，B是1位正整数。你需要输出商数Q和余数R，使得A = B * Q + R成立。
思路：一个简单的模拟，用字符串模拟数字就行了。

```cpp
#include <iostream>
#include <string>

using namespace std;

class Solution{
public:
    void compute(string a,int b){
        string c = "";
        int remain = 0;
        int temp = 0;
        for(int i=0;i<a.size();i++){
            temp = (a[i]-'0')+10*remain;
            remain = temp%b;
            if(i == 0&&temp/b == 0)
                continue;
            else{
                char d = (temp/b)+'0';
                c+=d;
            }
        }
        cout << c <<' '<< remain <<endl;
    }
};

int main()
{
    string a;
    int b;
    cin >> a >> b;
    Solution S;
    S.compute(a,b);
    return 0;
}

```
