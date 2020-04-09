```cpp
class Solution {
public:
    vector<int> twoSum(vector<int> &numbers, int target) {
        int n = numbers.size();
        unordered_map<int,int> mp;
        vector<int> res;
        for(int i = 0;i < n;i++){
            mp[numbers[i]] = i;
        }
        for(int i = 0;i < n;i++){
            int t = target - numbers[i];
            if(mp.count(t)&&mp[t]!=i){
                res.push_back(i+1);
                res.push_back(mp[t]+1);
                break;
            }
        }
        return res;
    }
};


```
