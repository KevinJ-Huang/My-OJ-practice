#### 小明很喜欢数学,有一天他在做数学作业时,要求计算出9~16的和,他马上就写出了正确答案是100。但是他并不满足于此,他在想究竟有多少种连续的正数序列的和为100(至少包括两个数)。没多久,他就得到另一组连续正数和为100的序列:18,19,20,21,22。现在把问题交给你,你能不能也很快的找出所有和为S的连续正数序列? Good Luck!
思路：分奇数偶数讨论，若除以的数为奇数，则必为以结果为中心的对称分布，若除以的数为偶数，则结果一定是带0.5的，除以的数的数目可以通过等差数列公式获得，对这些数进行遍历即可。
```cpp
#include <iostream>
#include <vector>
#include <math.h>
using namespace std;


class Solution {
public:
    vector<vector<int> > FindContinuousSequence(int sum) {
        vector<vector<int> > total;
        for(int i=int(sqrt(2*sum));i>=2;i--){
            if(((i%2==1)&&(sum%i==0))||((sum%i)*2==i)){
                vector<int> a;
                for(int j=0,k=(sum/i)-(i-1)/2; j<i;j++,k++)
                    a.push_back(k);
                total.push_back(a);
            }
        }
        return total;
    }
};

int main()
{
    Solution S;
    cout << S.FindContinuousSequence(100) << endl;
    return 0;
}
```
