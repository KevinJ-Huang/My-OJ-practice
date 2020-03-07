```cpp

class Solution {
public:
    int search(int A[], int n, int target) {
        int first = 0;
        int last = n-1;
        while(first <= last){
            int mid = first + (last-first)/2;
            if(A[mid] == target)
                return mid;
            if(A[first] <= A[mid]){
                if(target < A[mid]&&target >= A[first])
                    last = mid-1;
                else
                    first = mid+1;
            }
            else{
                if(target > A[mid]&&target <= A[last])
                    first = mid+1;
                else
                    last = mid-1;
            }
        }
        return -1;
    }
};

```
