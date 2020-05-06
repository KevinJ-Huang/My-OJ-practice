```cpp
class Solution {
public:
    /**
     * 
     * @param HP long长整型 HP
     * @param ACK long长整型 ACK
     * @param HP2 long长整型 HP2
     * @param ACK2 long长整型 ACK2
     * @return long长整型
     */
    long long Pokemonfight(long long HP, long long ACK, long long HP2, long long ACK2) {
        // write code here
        if(HP2 <= ACK)
            return -1;
        else if(ACK2 >= HP)
            return 1;
        long long numA = (HP2-ACK-1)/ACK;
        if(numA < 1)
            return -1;
        long long recover = numA*ACK2;
        long long res = (HP-2)/recover+HP/ACK2+(HP%ACK2>0?1:0);
        return res;
    }
};

```
