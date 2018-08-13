#### 给定区间[-2的31次方, 2的31次方]内的3个整数A、B和C，请判断A+B是否大于C。
使用long类型的数据代替即可。
```cpp
#include <iostream>

using namespace std;

class Solution{
public:
    bool compare(int a,int b,int c){
        long a1=a,a2=b,a3=c;
        if(a1+a2>a3)
           return true;
        else
           return false;
    }
};

int main()
{
    Solution S;
    int a,b,c,n;
    int k[n];
    cin >> n;
    for(int i=0;i<n;i++){
        cin>>a>>b>>c;
        k[i]=S.compare(a,b,c);
   }
   for(int i=0;i<n;i++){
        cout <<"Case #"<<i+1<<": "<<(k[i]>0?"true":"false")<< endl;
   }
    return 0;
}

```

