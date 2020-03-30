```cpp

struct Interval {
    int start;
    int end;
    Interval() : start(0), end(0) {}
    Interval(int s, int e) : start(s), end(e) {}
};

class Solution {
public:
    static bool compare(const Interval &a,const Interval &b){
        return a.start < b.start;
    }
    vector<Interval> merge(vector<Interval> &intervals) {
        vector<Interval> res;
        int n = intervals.size();
        if(n == 0)
            return res;
        sort(intervals.begin(),intervals.end(),compare);
        res.push_back(intervals[0]);
        for(int i = 1;i < n;i++){
            if(intervals[i].start<=res.back().end)
                res.back().end = max(res.back().end,intervals[i].end);
            else
                res.push_back(intervals[i]);
        }
        return res;
    }
};



```
