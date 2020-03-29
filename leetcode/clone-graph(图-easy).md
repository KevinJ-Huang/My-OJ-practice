```cpp
struct UndirectedGraphNode {
    int label;
    vector<UndirectedGraphNode *> neighbors;
    UndirectedGraphNode(int x) : label(x) {};
};

class Solution {
public:
    unordered_map<UndirectedGraphNode*,UndirectedGraphNode*> m;
    UndirectedGraphNode *dfs(UndirectedGraphNode *node){
        if(!node)
            return NULL;
        if(m.count(node))
            return m[node];
        UndirectedGraphNode *clone = new UndirectedGraphNode(node->label);
        m[node] = clone;
        for(int i=0;i<node->neighbors.size();i++){
            clone->neighbors.push_back(dfs(node->neighbors[i]));
        }
        return clone;
    }

    UndirectedGraphNode *cloneGraph(UndirectedGraphNode *node) {
        if(!node)
            return NULL;
        return dfs(node);
    }
};


```
