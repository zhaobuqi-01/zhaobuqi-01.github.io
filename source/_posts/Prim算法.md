---
title: Prim算法
date: 2021-01-03 23:16:29
tags:
categories: 数据结构
copyright:
---

## 算法思想

从连通网络N={v,E}中的某一个顶点v0出发，选择与他关联的具有最小权值的边（u0，v），将其顶点加入生成树的顶点集合U。以后每一步从一个顶点在U中，而另一个不在U的各条边选择权值最小的边（u，v），把它的顶点加入集合U中，这意味着（u，v）也加入生成树的边集合。如此继续下去，直到网络中的所有顶点都加入生成树的顶点集合U中为止。

# 代码

```c
void Prim(AdkMartix *G, int start) {
    struct {
        int adjvex;
        int lowcost;
    } closedge[MAXVEX];
    int m, min;
    closedge[start] = 0;//标志顶点u已经加入U生成树集合
    for (int i = 1; i <= G->vexnum; ++i) {
        if (i != start) {
            closedge[i].adjvex = start;
            closedge[i].lowcost = G->arcs[start][i];
        }
    }
    for (int i = 1; i <= G->vexnum; i++) {
        min = INFINTY;
        for (int j = 0; j <= G->vexnum; ++j) {
            if (closedge[j] != 0 && closedge[j].lowcost < min) {
                min = j;
                min = closedge[j].lowcost;
            }
        }
        closedge[m].lowcost = 0;
        for (int k = 0; k <= G->vexnum; ++k) {
            if (k != m && G->arcs[m][k] < closedge[k].lowcost) {
                closedge[i].lowcost = G->arcs[m][k];
                closedge[k].adjvex = m;
            }
        }
    }
}
```

