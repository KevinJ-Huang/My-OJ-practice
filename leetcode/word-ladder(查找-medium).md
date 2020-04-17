```cpp
class Solution {
public:
    int ladderLength(string start, string end, unordered_set<string> &dict) {
        queue<string>Q;
        Q.push(start);
        int res = 1;
        while(!Q.empty()){
            int qsize = Q.size();
            while(qsize--){
                string cur = Q.front();
                Q.pop();
                int len = cur.size();
                for(int i = 0;i < len;i++){
                    char ch = cur[i];
                    for(int j = 0;j < 26;j++){
                        cur[i] = 'a'+j;
                        if(cur == end) return res+1;
                        if(dict.find(cur)!=dict.end()){
                            Q.push(cur);
                            dict.erase(cur);
                        }
                    }
                    cur[i] = ch;
                }
            }
            res++;
        }
        return 0;
    }
};


```
