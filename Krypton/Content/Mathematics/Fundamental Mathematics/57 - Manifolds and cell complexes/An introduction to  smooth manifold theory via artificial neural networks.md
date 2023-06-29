#krypton #Tiago_Veríssimo 

#### Abstract
In this exposition we want to explore the relation between artificial neural networks and smooth manifolds.
To do this we will :
 - Define smooth manifolds
 - Explore some properties of smooth manifolds
 - Define what is a artificial neural network (ANN)
 - Relate the concept of ANN with smooth manifolds
 - Explore some consequences

##### Pre-requisites
This exposition requires the reader to have a basic understanding of:
- General Topology
- Real analysis
- Probability Theory
- Linear AL

# Introduction to manifolds

The reader should be aware that there will be an annoying amount of definitions at the beginning, however to do geometry we need to be conceptually equipped, after this the number of new concepts will eventually stabilise.

To talk about manifolds we have first to talk about what it means for a topological space $(X,\tau)$ to be **locally Euclidean**, we say that $(X,\tau)$ is **locally Euclidean** if there exists an integer $n \ne 0$ such that for every open neighbourhood $U \subseteq X$ we have that there exists an open neighbourhood $V\subseteq \mathbb{R}^n$ that is homoeomorphic to $U$, for short $U \cong V$.

### Definition : Topological Manifold

A n-topological manifold or only n-manifold for short is a topological space $(M,\tau)$ that has the following properties:
- $(M,\tau)$ is a Hausdorff space
- $(M,\tau)$ is locally Euclidean in $\mathbb{R}^{n}$
- $(M,\tau)$ is second countable

This might not seem like very reasonable to have as a definition at first sight, however we will eventually that this are the characteristics that we are interested.

A good example that the reader should have in mind when thinking about manifolds is a sphere $S^n$ as seen in the image

![[Pasted image 20230628001214.png|300]]


Turns out that we are very much interested in objects like the sphere which are in the geometrical sense smooth, think of no "pointy" things or sharp corners, again think on the sphere, objects with the qualitative aspects of the sphere are called **smooth manifolds**.
Before formally defining a smooth manifold we need yet again to define three important concepts in geometry:

- Charts
- Transition Maps
- Atlas

### Definition : Chart
Let $M$ be a topological $n$-manifold.
A coordinate chart (or just a chart) on $M$ is a pair $(\hat{U}, \varphi)$, where $U = \varphi^{-1}(\hat{U}) \subseteq \mathbb{R}^{n}$ and $\hat{U} \subseteq M$ and $\varphi: U \rightarrow \hat{U}$ is a homeomorphism.

### Definition : Smooth transition maps
Let $M$ be a topological $n$-manifold.
If $(U, \varphi),(V, \psi)$ are two charts such that $U \cap V \neq \varnothing$, the composite map $\psi^{-1} \circ \varphi: \varphi(U \cap V) \rightarrow \psi(U \cap V)$ is called the transition map from $\varphi$ to $\psi$ .
We say that these maps are smooth are $C^{\infty}$ compatible if the transition map $\psi^{-1} \circ \varphi$ is smooth in the real analysis sense.

### Definition : Atlas
We define an atlas for $M$ to be a collection of charts whose domains cover $M$.
An atlas $\mathcal{A}$ is called a smooth atlas if any two charts in $\mathcal{A}$ are smoothly compatible with each other, i.e.  any two charts within that atlas are $C^{\infty}$ compatible.

After defining this concepts we note that a given manifold can have many different smooth atlas, think of how many ways you can cover the sphere with different atlas, with this it seems that $M$ has many different smooth structures associated with it which from a mathematical point of view are almost identical, to get over this we have that we will define a **maximal smooth structure** $[A]$ for a manifold $M$ as a the union of all smooth atlas of $M$ that are $C^{\infty}$ compatible with a given smooth atlas $A$ for $M$.

##### Remark:
There can be for a given manifold $M$ many different maximal smooth structures.


We are finally in conditions of defining what is a **smooth manifold**.




### Definition : Smooth manifolds
Let $M$ be a manifold and consider an atlas $\tau$ of $M$.
Define as $\tau_{1}$ the set of all neighbourhoods that cover $M$ which belong to $\tau$. 
We say that a manifold $(M,\tau_{1})$ is smooth if we have that $\tau$ is a **maximal smooth structure** in $M$.

##### Remark
We say that a differentiable manifold $M$ satisfies the regularization condition if for all coordinate functions: the Jacobian of the transition functions $\phi_i \circ \phi_j^{-1}$ has a maximum rank.

From now onwards we will only consider **smooth manifolds** which have atlas of the type $A = \set{(\hat{U},\varphi):\hat{U} \in C}$ where $C$ is an open cover of $M$ .

## Tangent space

The tangent space $T_{p}M$ of a manifold $M$ at a point $p$ should be thought as the linear approximation of a given manifold $M$. 
Think of the sphere again you should think of the tangent space as the set of all vectors that live in the tangent plane, check the image below.

![[Pasted image 20230629173427.png|200]]


To put the concepts more formally, we consider a manifold $M$ which has has a local parametrization $\phi: \mathcal{U} \rightarrow \mathcal{M}$, with $\mathcal{U} \subset \mathbb{R}^n$ open set, then the vector tangent to the $k$ th coordinate curve
$$
h \rightarrow \phi\left(x_1, \ldots, x_k+h, \ldots, x_n\right)
$$
is given by (if you want a rigorous approach consider the reference )
$$
T_k(p)=\frac{\partial \phi}{\partial x_k}(p), \quad p=\phi(x) .
$$
If the manifold satisfies the regularity condition that $\phi$ has a Jacobian matrix of maximum rank at $p$, then the tangent vectors $\left\{T_1(p), \ldots, T_n(p)\right\}$ are linearly independent and in particular form a basis form a basis for $T_{p}M$.

We call tangent bundle the set $TM$ defined as

$$
TM = \cup_{p \in M} T_{p}M
$$
this construction is from times to time useful to be formal.

Consider now a curve $c(t)$ in $M$ where $t \in [a,b]\subseteq \mathbb{R}$ if we are interested in the tangent vector at each point $p \in M$ we have a local description of the vectors as (if you want a rigorous approach check for )
$$
\dot{c}(t)=\sum_{k=1}^n \dot{c}^k(t) T_k(c(t))
$$
This idea of tangent space naturally defines a tangent vector field, $X: M \rightarrow TM$, which a smooth assignment of a tangent vector $X_p \in T_p \mathcal{M}$, at each point $p \in \mathcal{M}$. 
In local coordinates this writes as $X_p=$ $\sum_{k=1}^n X^k(p) T_k(p)$. 

## Riemannian metric

We will talk about the concept of a metric in a manifold $M$.
When we are considering distances in a plane we usually use the Euclidean metric to measure the distance two points in a plane for example, however when it comes to measuring distance in manifolds it is not so easy, given that we have to account for curvature while measuring distance, it is no longer the length of a straight line between points that givens you the distance we need to account for curves which may curvatures in them as well.
To take this in consideration mathematicians came up with the concept of a metric 

$$
g = (g_{ij})_{i,j \in I} = \begin{pmatrix}
g_{11} & g_{12} & \cdots & g_{1n} \\
g_{21} & g_{22} & \cdots & g_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
g_{n1} & g_{n2} & \cdots & g_{nn}
\end{pmatrix}

$$

which is a matrix that enables to measure distances between two points in the following way. 
Firstly we need to consider a curve $c(t)$ in the manifold and we consider the length of the tangent vector as

$$
\|\dot{c}(t)\|_g=\left(\sum_{i, j=1}^n g_{i j}(c(t)) \dot{c}(t)^i \dot{c}(t)^j\right)^{1 / 2}=g(\dot{c}(t), \dot{c}(t))^{1 / 2}
$$

with this we can make measure the length of  $c(t)$ in $M$  in an interval $[a,b]\subseteq \mathbb{R}$ via

$$
L(c)=\int_a^b\|\dot{c}(t)\|_g d t
$$

with this way of measuring distances in manifolds we can introduce the concept of **Riemannian Distance** between points $A,B \in M$, which is given by 

$$
d(A, B)=\inf _c\{L(c) ; c:[a, b] \rightarrow \mathcal{M}, c(a)=A, c(b)=B\} .
$$

So the **distance between two points in a manifold $M$ is given by length of the shortest curve that unites the points.**
We call the pair $(M,g)$ a **Riemannian manifold**.

##### Remark
Note that the length of the tangent vector is dependent on the definition of the metric.




## Geodesics

