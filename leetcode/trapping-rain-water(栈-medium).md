```cpp
class Solution {
public:
    int trap(int A[], int n) {
        stack<int> s;
        int res = 0;
        for(int i = 0;i < n;i++){
            while(!s.empty()&&A[s.top()]<A[i]){
                int t = s.top();
                s.pop();
                while(!s.empty()&&A[s.top()]<=A[t])
                    s.pop();
                if(!s.empty())
                    res+=(min(A[s.top()],A[i])-A[t])*(i-s.top()-1);
            }
            s.push(i);
        }
        return res;
    }
};


```
