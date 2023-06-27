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

![[Pasted image 20230627222346.png|300]]


Turns out that we are very much interested in objects like the sphere which are in the geometrical sense smooth, think of no "pointy" things or sharp corners, again think on the sphere, objects with the qualitative aspects of the sphere are called **smooth manifolds**.
Before formally defining a smooth manifold we need yet again to define two important concepts in geometry:

- Charts
- Transition Maps
- Atlas

### Definition : Chart
Let $M$ be a topological $n$-manifold.
A coordinate chart (or just a chart) on $M$ is a pair $(U, \varphi)$, where $U$ is an open subset of $M$ and $\varphi: U \rightarrow \widehat{U}$ is a homeomorphism from $U$ to an open subset $\hat{U}=\varphi(U) \subseteq \mathbb{R}^n$.

### Definition : Smooth transition maps
Let $M$ be a topological $n$-manifold.
If $(U, \varphi),(V, \psi)$ are two charts such that $U \cap V \neq \varnothing$, the composite map $\psi \circ \varphi^{-1}: \varphi(U \cap V) \rightarrow \psi(U \cap V)$ is called the transition map from $\varphi$ to $\psi$ .
We say that these maps are smooth are $C^{\infty}$ compatible if the transition map $\psi \circ \varphi^{-1}$ is smooth in the real analysis sense.

### Definition : Atlas
We define an atlas for $M$ to be a collection of charts whose domains cover $M$.
An atlas $\mathcal{A}$ is called a smooth atlas if any two charts in $\mathcal{A}$ are smoothly compatible with each other, i.e.  any two charts within that atlas are $C^{\infty}$ compatible.

After defining this concepts we note that a given manifold can have many different smooth atlas, think of how many ways you can cover the sphere with different atlas, with this it seems that $M$ has many different smooth structures associated with it which from a mathematical point of view are almost identical, to get over this we have that we will define a **maximal smooth structure** $[A]$ for a manifold $M$ as a the union of all smooth atlas of $M$ that are $C^{\infty}$ compatible with a given smooth atlas $A$ for $M$.

##### Note:
There can be for a given manifold $M$ many different maximal smooth structures.


We are finally in conditions of defining what is a **smooth manifold**.



### Definition : Smooth manifolds
We say that a manifold $(M,\tau)$ is smooth if we have that $\tau$ is a **maximal smooth structure** in $M$.


