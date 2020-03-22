```cpp
class Solution {
public:
    int largestRectangleArea(vector<int> &height) {
        stack<int> s;
        int n = height.size(),res = 0, w = 0;
        for(int i = 0;i < n;i++){
            while(!s.empty()&&height[s.top()]>=height[i]){
                int h = height[s.top()];
                s.pop();
                if(s.empty())
                    w = i;
                else
                    w = i-1-s.top();
                res = max(res,h*w);
            }
            s.push(i);
        }
        while(!s.empty()){
            int h = height[s.top()];
                s.pop();
            if(s.empty())
                w = n;
            else
                w = n-1-s.top();
            res = max(res,h*w);
        }
        return res;
    }
};


```
