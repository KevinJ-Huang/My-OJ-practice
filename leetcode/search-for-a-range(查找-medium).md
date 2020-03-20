```cpp
class Solution {
public:
    vector<int> searchRange(int A[], int n, int target) {
        vector<int> res(2,-1);
        if(n<0)
            return res;
            
        int start = 0;
        int last = n-1;
        while(start <= last){
            int mid = start+(last-start)/2;
            if(A[mid] < target)
                start = mid+1;
            else
                last = mid-1;
        }
        
        int start2 = 0;
        int last2 = n-1;
        while(start2 <= last2){
            int mid2 = start2+(last2-start2)/2;
            if(A[mid2] > target)
                last2 = mid-1;
            else
                start2 = mid+1;
        }
        if(start <= last2){
            res[0] = start;
            res[1] = last2;
        }
        return res;
    }
};


```
