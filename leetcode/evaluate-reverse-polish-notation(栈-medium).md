```cpp

class Solution {
public:
    int evalRPN(vector<string> &tokens) {
        stack<int> nums;
        for(auto token:tokens){
            if(token == "+"||token=="-"||token =="*"|| token == "/"){
                int a,b,res;
                b = nums.top();
                nums.pop();
                a = nums.top();
                nums.pop();
                if(token == "+")
                    res=a+b;
                else if(token == "-")
                    res=a-b;
                else if(token == "*")
                    res=a*b;
                else
                    res=a/b;
                nums.push(res);
            }
            else{
                nums.push(atoi(token.c_str()));
            }
        }
        return nums.top();
    }
};


```
