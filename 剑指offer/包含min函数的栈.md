#定义栈的数据结构，请在该类型中实现一个能够得到栈最小元素的min函数。
思路：使用两个栈，将送入的数据放入辅助栈，将辅助栈的入栈值和目标栈的栈顶进行比较，若小于，则将辅助栈的入栈值送入目标栈。
```cpp
#include <iostream>
#include <stack>

using namespace std;

class Solution {
public:
    stack<int> datastack,minstack;
    void push(int value) {
        datastack.push(value);
        if(minstack.empty())
            minstack.push(value);
        else{
           if(value > minstack.top())
               minstack.push(value);
        }
    }
    void pop() {
        datastack.pop();
        minstack.pop();
    }
    int top() {
        return datastack.top();
    }
    int min() {
        return minstack.top();
    }
};

int main()
{
    cout << "Hello world!" << endl;
    return 0;
}

```
