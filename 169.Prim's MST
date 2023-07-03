#include <bits/stdc++.h> 

vector<pair<pair<int, int>, int>> calculatePrimsMST(int n, int m, vector<pair<pair<int, int>, int>> &g)
{ 
    vector<pair<int, int>> adj[n+1];
    for(auto it: g){
        adj[it.first.first].push_back({it.first.second, it.second});
        adj[it.first.second].push_back({it.first.first, it.second});
    }
     priority_queue<pair<pair<int, int>, int>, vector<pair<pair<int, int>, int>>, greater<pair<pair<int, int>, int>>> pq;
        vector<int> vist(n+1, 0);
        vector<pair<pair<int, int>, int>> mst;
        // {wt, node}
        pq.push({{0, 1}, -1}); 
        while(!pq.empty()){
            auto it = pq.top();
            pq.pop();
            
            int wt = it.first.first;
            int node = it.first.second;
            int parent = it.second;
            
            if(vist[node] == 1) continue; // if already visisted
            vist[node] = 1; // else mark it visited only after popping out of the min-heap
            if(parent != -1) mst.push_back({{parent, node}, wt});
            // sum += wt; // add the edge weight to sum
            for(auto it: adj[node]){
                int adjNode = it.first;
                int edgwt = it.second;
                
                if(!vist[adjNode])
                    pq.push({{edgwt, adjNode}, node});
            }
        }
        
        return mst;
}
