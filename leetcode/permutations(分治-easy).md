```cpp

class Solution {
public:
    vector<vector<int> > permute(vector<int> &num) {
        vector<vector<int>> res;
        permutes(res,num,0);
        return res;
    }
    void permutes(vector<vector<int>> &res,vector<int> &num,int s){
        if(s == num.size()-1)
            res.push_back(num);
        else{
            for(int i = s;i < num.size();i++){
                swap(num[s],num[i]);
                permutes(res,num,s+1);
                swap(num[s],num[i]);
            }
        }
    }
};


```
