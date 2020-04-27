```cpp
class Solution {
public:
    bool IsContinuous( vector<int> numbers ) {
        int n = numbers.size();
        if(n!=5) return false;
        sort(numbers.begin(),numbers.end());
        int jocker = 0;
        while(numbers[jocker]==0)
            jocker++;
        for(int i = jocker;i < 4;i++){
            if(numbers[i]==numbers[i+1])
                return false;
        }
        if(numbers[4]-numbers[jocker]>4)
            return false;
        return true;
    }
};
```
