# Graph Theory
- A **graph** is a set of nodes connected by branches.
- Graphs are either **connected** or **unconnected**
- Graphs are either **directed** or **undirected**  

A **subgraph** is a part of a graph. There are two types of importance to us:
1. A **tree** is a **connected** subgraph containing **all nodes**, with **no loops**.
2. **Co-Tree** is the rest of the graph. (Complement of Tree)

**Tree Branches** are branches in the tree. While, tree links are branches outside the tree.

For a tree with **N** nodes & **B** branches and **L** links,
- $ N = B $
- $ L = B – (N-1) = B – N + 1 $

There are 3 matrices to describe network graphs
1. **Incidence Matrix**
2. **Fundamental Loop** or **Tie Set Matrix**
3. **Fundamental Cut set Matrix**

**Incidence Matrix** is a matrix with **N rows** & **B columns** and its values are one of **{-1,0,1}**, representing the relation between N & B
- **+1** if B is directed **towards** N
- **-1** if B is directed **out of** N
- **0**  if B is **NOT** connected to N

**Fundamental Loop** is a loop composed of some of the tree branches and a link. So for each graph the number of fundamnetal loops equals number of links.

**Fundamental Loop Matrix** is a matrix whose each row represents one the fundamental loops. <br/>
$ M_{i,j} = relation(i^{th} Fundamental Loop , j^{th} Edge In Graph) $ <br/>
Where $ relation(loop,edge) $ = 
- **+1** if *edge* has same direction as *loop*
- **-1** if *edge* has opposite direction to *loop*
- **0**  if *edge* is **NOT** in *loop*.

Given that loop's direction is same as link's direction.