```cpp
class Solution {
public:
    vector<vector<int> > threeSum(vector<int> &num) {
        vector<vector<int>> res;
        int n = num.size();
        if(n<3)
            return res;
        sort(num.begin(),num.end());
        for(int i = 0;i < n-2;i++){
            if(i > 0&&num[i] == num[i-1])
                continue;
            int left = i+1;
            int right = n-1;
            while(left < right){
                int sum = num[i]+num[left]+num[right];
                if(sum == 0){
                    vector<int> cur{num[i],num[left],num[right]};
                    res.push_back(cur);
                    while(left<right&&num[left]==num[left+1])
                        left++;
                    while(left<right&&num[right]==num[right-1])
                        right--;
                    left++;
                    right--;
                }
                else if(sum < 0)
                    left++;
                else
                    right--;
            }
        }
        return res;
    }
};


```
