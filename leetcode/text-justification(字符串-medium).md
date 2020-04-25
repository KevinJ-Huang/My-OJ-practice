```cpp

class Solution {
public:
    vector<string> fullJustify(vector<string> &words, int L) {
        int n = words.size();
        vector<string> res;
        int j = 0;
        for(int i = 0;i < n;i=j){
            int width = 0;
            for(j = i;j < n&&width+words[j].size()+j-i<=L;j++)
                width+=words[j].size();
            int space = 1,extra = 0;
            if(j-i!=1&&j!=words.size()){
                space = (L-width)/(j-i-1);
                extra = (L-width)%(j-i-1);
            }
            string line(words[i]);
            for(int k =i+1;k<j;k++){
                line+=string(space,' ');
                if(extra-->0)
                    line+=" ";
                line+=words[k];
            }
            line += string(L-line.size(),' ');
            res.push_back(line);
        }
        return res;
    }
};

```
