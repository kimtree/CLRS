## 26.1 Flow networks

### 26.1-1

> Show that splitting an edge in a flow network yields an equivalent network. More formally, suppose that flow network $$G$$ contains edge $$(u, v)$$, and we create a new flow network $$G'$$ by creating a new vertex $$x$$ and replacing $$(u, v)$$ by new edges $$(u, x)$$ and $$(x, v)$$ with $$c(u, x) = c(x, v) = c(u, v)$$. Show that a maximum flow in $$G'$$ has the same value as a maximum flow in $$G$$.

$$f(u, x) = f(x, v)$$.

### 26.1-2

> Extend the flow properties and definitions to the multiple-source, multiple-sink problem. Show that any flow in a multiple-source, multiple-sink flow network corresponds to a flow of identical value in the single-source, single-sink network obtained by adding a supersource and a supersink, and vice versa.

Capacity constraint: for all $$u, v \in V$$, we require $$0 \le f(u, v) \le c(u, v)$$.

Flow conservation: for all $$u \in V - S - T$$, we require $$\sum_{v \in V} f(v, u) = \sum_{v \in V} f(u, v)$$.

### 26.1-3

> Suppose that a flow network $$G = (V, E)$$ violates the assumption that the network contains a path $$s \leadsto v \leadsto t$$ for all vertices $$v \in V$$. Let $$u$$ be a vertex for which there is no path $$s \leadsto u \leadsto t$$. Show that there must exist a maximum flow $$f$$ in $$G$$ such that $$f(u, v) = f(v, u) = 0$$ for all vertices $$v \in V$$.

Cannot flow in or flow out.

### 26.1-4

> Let $$f$$ be a flow in a network, and let $$\alpha$$ be a real number. The __*scalar flow product*__, denoted $$\alpha f$$, is a function from $$V \times V$$ to $$\mathbb{R}$$ defined by
> 
> $$(\alpha f)(u, v) = \alpha \cdot f(u, v)$$.
> 
> Prove that the flows in a network form a __*convex set*__. That is, show that if $$f_1$$ and $$f_2$$ are flows, then so is $$\alpha f_1 + (1 - \alpha) f_2$$ for all $$\alpha$$ in the range $$0 \le \alpha \le 1$$.

### 26.1-5

> State the maximum-flow problem as a linear-programming problem.

$$
\begin{array}{ll}
\max & \displaystyle \sum_{v \in V} f(s, v) - \sum_{v \in V} f(v, s) \\
s.t. & 0 \le f(u, v) \le c(u, v) \\
& \displaystyle \sum_{v \in V} f(v, u) - \sum_{v \in V} f(u, v) = 0
\end{array}
$$

### 26.1-6

> Professor Adam has two children who, unfortunately, dislike each other. The problem is so severe that not only do they refuse to walk to school together, but in fact each one refuses to walk on any block that the other child has stepped on that day. The children have no problem with their paths crossing at a corner. Fortunately both the professor's house and the school are on corners, but beyond that he is not sure if it is going to be possible to send both of his children to the same school. The professor has a map of his town. Show how to formulate the problem of determining whether both his children can go to the same school as a maximum-flow problem.

The capacity of each path is 1, the maximum-flow should be greater than 1.

### 26.1-7

> Suppose that, in addition to edge capacities, a flow network has __*vertex capacities*__. That is each vertex $$v$$ has a limit $$l(v)$$ on how much flow can pass though $$v$$. Show how to transform a flow network $$G = (V, E)$$ with vertex capacities into an equivalent flow network $$G' = (V', E')$$ without vertex capacities, such that a maximum flow in $$G'$$ has the same value as a maximum flow in $$G$$. How many vertices and edges does $$G'$$ have?

For each vertex $$v$$, transform it to an edge $$(v, v')$$ with capacity $$l(v)$$. $$G'$$ has $$2V$$ vertices and $$V + E$$ edges.
