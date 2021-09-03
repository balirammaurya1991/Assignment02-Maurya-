# Baliram Maurya 
###### California Silicon Valley 
Silicon valley is a hub for software industries even it's headquater of some manny giant IT companies. It attracts IT professionals from accross the world. I like the this place the reason is there is so many opportunities for IT **professionals** as well as business owners. It good place to grab a better **opportunities**.

*** 
###### Travel Instruction from Los Angeles to Maryville(Northwest)

***

 There are many ways to travel from Los Angeles to Marryville:

     1. By Air
        1. Book the flight from Las Angeles Aiport 
        2. Choose destination Airport Kansas city
        3. Take Taxi from Kansas city to Maryville 
     2. By Bus
     3. By Car
     4. By Train

     
###### Things to enjoy:

    * Play Game

    * Fix something

    * Play an instrument

    * Sing to yourself

    * Work in a garden

    * Find ways to recycle stuff

    * Write a poem or short story

    * Talk to friends

[Take me to Aboutme page](AboutMe.md)


***

###### Food/Drinks list:
| Food/Drink   | Location    | Amount|
| -----------  | --------    |-------|
| Apple juice  | Walmart     | 2.0 $|
| Cheese Burger| McDonald    | 1.5 $ 
| Pizza        | Dominoz     | 2 $ |
| Pasta        | Dinning Hall|2 $| 


***
## Quote:
> All art is a kind of confession

*James Baldwin*

> Impossible is just an opinion

*Paulo Coelho*

*** Graph spanning

> Here we describe the algorithm in its simplest form. The minimum spanning tree is built gradually by adding edges one at a time. At first the spanning tree consists only of a single vertex (chosen arbitrarily). Then the minimum weight edge outgoing from this vertex is selected and added to the spanning tree. After that the spanning tree already consists of two vertices. Now select and add the edge with the minimum weight that has one end in an already selected vertex (i.e. a vertex that is already part of the spanning tree), and the other end in an unselected vertex. And so on, i.e. every time we select and add the edge with minimal weight that connects one selected vertex with one unselected vertex. The process is repeated until the spanning tree contains all vertices (or equivalently until we have n−1 edges).

> In the end the constructed spanning tree will be minimal. If the graph was originally not connected, then there doesn't exist a spanning tree, so the number of selected edges will be less than n−1.

[source link ](https://cp-algorithms.com/graph/mst_prim.html#toc-tgt-1)

``` 
int n;
vector<vector<int>> adj; // adjacency matrix of graph
const int INF = 1000000000; // weight INF means there is no edge

struct Edge {
    int w = INF, to = -1;
};

void prim() {
    int total_weight = 0;
    vector<bool> selected(n, false);
    vector<Edge> min_e(n);
    min_e[0].w = 0;

    for (int i=0; i<n; ++i) {
        int v = -1;
        for (int j = 0; j < n; ++j) {
            if (!selected[j] && (v == -1 || min_e[j].w < min_e[v].w))
                v = j;
        }

        if (min_e[v].w == INF) {
            cout << "No MST!" << endl;
            exit(0);
        }

        selected[v] = true;
        total_weight += min_e[v].w;
        if (min_e[v].to != -1)
            cout << v << " " << min_e[v].to << endl;

        for (int to = 0; to < n; ++to) {
            if (adj[v][to] < min_e[to].w)
                min_e[to] = {adj[v][to], v};
        }
    }

    cout << total_weight << endl;
}

```
[source code link](https://cp-algorithms.com/graph/mst_prim.html#toc-tgt-1)