#include<bits/stdc++.h>
bool helper(int root,vector<int>adj[],vector<int>&col){
    queue<int>q;
    q.push(root);
    col[root]=1;
    
    while(!q.empty()){
        int node=q.front();
        q.pop();
        for(auto it:adj[node]){
            if(col[it]==-1){
                col[it]=1-col[node];
                q.push(it);
            }
            else if(col[it]==col[node]){
                return false;
            }
        }
    }
    return true;
}

bool isGraphBirpatite(vector<vector<int>> &edges) {
    int n=edges[0].size();
    vector<int>adj[n];
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            if(edges[i][j]==1){
                adj[i].push_back(j);
                adj[j].push_back(i);
            }
        }
    }
    vector<int>col(n,-1);
    for(int i=0;i<n;i++){
        if(col[i]==-1){
            if(helper(i,adj,col)==false){
                return false;
            }
        }
    }
    return true;
}
