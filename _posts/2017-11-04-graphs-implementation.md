---
layout: post
title: Graph implementation in the two possible ways
categories: graphs
---

{{ page.title }}
================

Adjacency list and Adjacency matrix implementation of Graphs. The choice of the graph representation is situation specific and totally depends on the type of operations to be performed and ease of use.

Adjacency martix implementation
-------------------------------

Know you know how that is. Just in case, a[i][j] = 1 shows there's a edge between i and j nodes. Remember to change the MAX to the required number.

~~~~
bool A[MAX][MAX];

void initialize() {
    for(int i = 0;i < MAX;++i)
        for(int j = 0;j < MAX;++j)
            A[i][j] = false;
}

// Code for Main function

    int x, y, nodes, edges;
    initialize();       
    cin >> nodes;       
    cin >> edges;
    for(int i = 0;i < edges;++i) {
        cin >> x >> y;
        A[x][y] = true;
    }
    
~~~~

Removing an edge takes O(1) time in this implementation. Queries like whether there is an edge from vertex ‘u’ to vertex ‘v’ are efficient and can be done O(1). Heavy memory utilisation. 

Adjacency list implemenation
----------------------------

V in the function call represents the number of nodes - remember to change the placeholder to the required value or input. Don''t forget to account of the fact that the given graph deals entirely from index 0. Vectors used. Code for Adjacency list implementation taken from [GeeksforGeeks](http://www.geeksforgeeks.org/graph-implementation-using-stl-for-competitive-programming-set-2-weighted-graph/), presented with minor modifications. 

~~~~
#include<bits/stdc++.h>
using namespace std;
 
void addEdge(vector<int> adj[], int u, int v)
{
    adj[u].push_back(v);
    adj[v].push_back(u);
}
 
 
// Code for main function - function calls
    vector<int> adj[V];
    addEdge(adj, a, b);
    DFS(adj, V);
    
~~~~
