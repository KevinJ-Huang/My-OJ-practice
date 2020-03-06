```cpp

class Solution {
public:
    bool search(int A[], int n, int target) {
        int first = 0,last = n-1;
        while(first <= last){
            int mid = first + (last-first)/2;
            if(A[mid] == target)
                return true;
            if(A[first] == A[mid]&&A[last] == A[mid]){
                first++;
                last--;
            }
            else if(A[first] <= A[mid]){
                if(A[mid]>target&&A[first]<=target)
                     last = mid-1;
                else
                     first = mid+1;
            }
            else if(A[first] >= A[mid]){
                 if(target <= A[last]&& A[mid] < target)
                     first = mid+1;
                 else
                     last = mid-1;
            }
        }
        return false;
    }
};

```
