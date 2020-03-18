```cpp
class Solution {
public:
    vector<vector<int> > permuteUnique(vector<int> &num) {
        vector<vector <int> > res;
        sort(num.begin(),num.end());
        permute(res,num,0);
        sort(res.begin(),res.end());
        res.erase(unique(res.begin(),res.end()),res.end());
        return res;
    }
    void permute(vector<vector<int> > &res,vector<int> num,int s){
        if(s == num.size())
            res.push_back(num);
        else{
            permute(res,num,s+1);
            for(int i = s+1;i < num.size();i++){
                if(num[i] == num[s])
                    continue;
                swap(num[s],num[i]);
                permute(res,num,s+1);
                swap(num[s],num[i]);
            }
        }
    }
};


```
