```cpp
class Solution {
public:
    string addBinary(string a, string b) {
        int length = max(a.size(),b.size());
        char flag = '0';
        while(length > a.size())
            a = "0"+a;
        while(length > b.size())
            b = "0"+b;
        string res(length+1,' ');
        for(int i = length-1;i >= 0;i--){
            int sum = a[i] + b[i] + flag - 3*'0';
            if(sum == 3){
                res[i+1] = '1';
                flag = '1';
            }
            else if(sum == 2){
                res[i+1] = '0';
                flag = '1';
            }
            else{
                res[i+1] = sum+'0';
                flag = '0';
            }
        }
        if(flag == '1')
            res[0] = '1';
        else
            res = res.substr(1);
        return res;
    }
};



```
