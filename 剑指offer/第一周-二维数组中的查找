#include <iostream>
#include <vector>
#define W 4
#define H 4

using namespace std;
int target = 10;
vector <vector<int> > a(W);


class Solution{
public:
    bool Find(int target,vector<vector<int> >array){
        if(array.empty()) return false;
        for(int i = 0;i < array.size();i++){
            if(array[i].empty()) continue;
            else if(target >= array[i][0])
            {
                if(target <= array[i][array[i].size()-1])
                {
                    for(int j = array[i].size()-1;j >= 0;j--){
                        if(target == array[i][j]) return true;
                        else if(target > array[i][j])
                            break;
                    }
                }
                else
                    continue;
            }
            else return false;
        }
        return false;
    }

};

int main()
{
    for (int i = 0; i < W; i++)
             a[i].resize(H);
    int t=0;
    for(int i = 0;i < W;i++){
        for(int j=0;j < H;j++){
            a[i][j] = t++;
        }
    }
    Solution S;
    cout << S.Find(target,a) <<endl;
    return 0;
}
