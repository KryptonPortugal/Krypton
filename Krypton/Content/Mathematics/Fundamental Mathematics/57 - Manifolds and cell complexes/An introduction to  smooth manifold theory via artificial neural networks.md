#Tiago_Veríssimo 

## Author: Tiago Mesquita Santos Veríssimo

#### Abstract
In this exposition we want to explore the relation between artificial neural networks and smooth manifolds.
To do this we will :
 - Define smooth manifolds
 - Explore some properties of smooth manifolds
 - Define what is a artificial neural network (ANN)
 - Relate the concept of ANN with smooth manifolds
 - Explore the relation between geodesic and ANN fine-tunning

##### Pre-requisites
This exposition requires the reader to have a basic understanding of:
- General Topology
- Real analysis
- Probability Theory
- Linear Algebra

## Introduction to manifolds

The reader should be aware that there will be an annoying amount of definitions at the beginning, however to do geometry we need to be conceptually equipped.

To talk about manifolds we have first to talk about what it means for a topological space $(X,\tau)$ to be **locally Euclidean**, we say that $(X,\tau)$ is **locally Euclidean** if there exists an integer $n \ne 0$ such that for every open neighbourhood $U \subseteq X$ we have that there exists an open neighbourhood $V\subseteq \mathbb{R}^n$ that is homoeomorphic to $U$, for short $U \cong V$.

### Definition : Topological Manifold

A n-topological manifold or only n-manifold for short is a topological space $(M,\tau)$ that has the following properties:
- $(M,\tau)$ is a Hausdorff space
- $(M,\tau)$ is locally Euclidean in $\mathbb{R}^{n}$
- $(M,\tau)$ is second countable

This might not seem like very reasonable to have as a definition at first sight, however we will eventually that this are the characteristics that we are interested.

A good example that the reader should have in mind when thinking about manifolds is a sphere $S^2$ as seen in the image

![[Pasted image 20230628001214.png|200]]


Turns out that we are very much interested in objects like the sphere which are in the geometrical sense smooth, think of no "pointy" things or sharp corners, again think on the sphere, objects with the qualitative aspects of the sphere are called **smooth manifolds**.
Before formally defining a smooth manifold we need to define three important concepts in geometry:

- Charts
- Transition Maps
- Atlas

### Definition : Chart
Let $M$ be a topological $n$-manifold.
A coordinate chart (or just a chart) on $M$ is a pair $(\hat{U}, \varphi)$, where $U = \varphi^{-1}(\hat{U}) \subseteq \mathbb{R}^{n}$ and $\hat{U} \subseteq M$ and $\varphi: U \rightarrow \hat{U}$ is a homeomorphism.

### Definition : Smooth transition maps
Let $M$ be a topological $n$-manifold.
If $(U, \varphi),(V, \psi)$ are two charts such that $U \cap V \neq \varnothing$, the composite map $\psi^{-1} \circ \varphi: \varphi^{-1}(U \cap V) \rightarrow \psi^{-1}(U \cap V)$ is called the transition map from $\varphi$ to $\psi$ .
We say that these maps are smooth are $C^{\infty}$ compatible if the transition map $\psi^{-1} \circ \varphi$ is smooth in the real analysis sense.

### Definition : Atlas
We define an atlas for $M$ to be a collection of charts whose domains cover $M$.
An atlas $\mathcal{A}$ is called a smooth atlas if any two charts in $\mathcal{A}$ are smoothly compatible with each other, i.e. any two charts within that atlas are $C^{\infty}$ compatible.

After defining this concepts we note that a given manifold can have many different smooth atlas, think of how many ways you can cover the sphere with different atlas, with this it seems that $M$ has many different smooth structures associated with it which from a mathematical point of view are almost identical, to get over this we have that we will define a **maximal smooth structure** $[A]$ for a manifold $M$ as a the union of all smooth atlas of $M$ that are $C^{\infty}$ compatible with a given smooth atlas $A$ for $M$.

##### Remark:
There can be for a given manifold $M$ many different maximal smooth structures.

We are finally in conditions of defining what is a **smooth manifold**.

### Definition : Smooth manifolds
Let $M$ be a manifold and consider an atlas $\tau$ of $M$.
We say that a manifold $(M,\tau)$ is smooth if we have that $\tau$ is a **maximal smooth structure** in $M$.

##### Remark
We say that a differentiable manifold $M$ satisfies the **regularization** condition if for all coordinate functions: the Jacobian of the transition functions $\phi_i \circ \phi_j^{-1}$ has a maximum rank.

From now onwards we will only consider **smooth manifolds** which have a atlas of the type $A = \set{(\hat{U},\varphi):\hat{U} \in C}$ where $C$ is an open cover of $M$ and $\varphi$ is a smooth chart map.

## Tangent space

The tangent space $T_{p}M$ of a manifold $M$ at a point $p$ should be thought as the linear approximation of a given manifold $M$. 
Think of the sphere again you should think of the tangent space as the set of all vectors that live in the tangent plane, check the image below.

![[Pasted image 20230629173427.png|200]]


To put the concepts more formally, we consider a manifold $M$ which has has a local parametrization $\phi: \mathcal{U} \rightarrow \mathcal{M}$, with $\mathcal{U} \subset \mathbb{R}^n$ open set, then the vector tangent to the $k$ th coordinate curve
$$
h \rightarrow \phi\left(x_1, \ldots, x_k+h, \ldots, x_n\right)
$$
is given by
$$
T_k(p)=\frac{\partial \phi}{\partial x_k}(p), \quad p=\phi(x) . \tag{1}
$$
If the manifold satisfies the regularity condition that $\phi$ has a Jacobian matrix of maximum rank at $p$, then the tangent vectors $\left\{T_1(p), \ldots, T_n(p)\right\}$ are linearly independent and in particular form a basis form a basis for $T_{p}M$.

We call tangent bundle the set $TM$ defined as
$$
TM = \cup_{p \in M} T_{p}M
$$
this construction is from times to time useful to be formal.

Consider now a curve $c(t)$ in $M$ where $t \in [a,b]\subseteq \mathbb{R}$ if we are interested in the tangent vector at each point $p \in M$ we have a local description of the vectors as
$$
\dot{c}(t)=\sum_{k=1}^n \dot{c}^k(t) T_k(c(t))
$$
This idea of tangent space naturally defines a tangent vector field, $X: M \rightarrow TM$, which a smooth assignment of a tangent vector $X_p \in T_p \mathcal{M}$, at each point $p \in \mathcal{M}$. 
In local coordinates this writes as $X_p=$ $\sum_{k=1}^n X^k(p) T_k(p)$. 

## Riemannian metric

We will talk about the concept of a metric in a manifold $M$.
When we are considering distances in a plane we usually use the Euclidean metric to measure the distance between two points in a plane, for example, however when it comes to measuring distance in manifolds it is not so easy, given that we have to account for curvature while measuring distance, it is no longer the length of a straight line between points that givens you the distance we need to account for curves which may curvatures in them as well.
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

with this we can measure the length of $c(t)$ in $M$  in an interval $[a,b]\subseteq \mathbb{R}$ via

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

Equipped with the notion of distance between points we want to study the curves that describe the shortest path between points.
If the points are close enough, there is always a geodesic between them and this is unique. 
In local coordinates the geodesic $c(t)$ can be described by a system of nonlinear equations as

$$
\ddot{c}^k(t)+\sum_{i, j} \Gamma_{i j}^k \dot{c}^i(t) \dot{c}^j(t)=0, \quad 1 \leq k \leq n
$$

where $\Gamma_{i j}^k=\Gamma_{i j}^k(c(t))$ are the Christoffel symbols of second kind, they are given by the Levi-Civita formula
$$
\Gamma_{i j}^k=\frac{1}{2} g^{k r}\left(\frac{\partial g_{i r}}{\partial x_j}+\frac{\partial g_{j r}}{\partial x_i}-\frac{\partial g_{i j}}{\partial x_r}\right),
$$
where $\left(x_1, \ldots, x_n\right)$ represent the local coordinates on the manifold, we will talk more about Christoffel symbols next chapter Since they depend on the metric coefficients $g_{i j}$, the Christoffel symbols are intrinsic.

## Levi-Civita connection

Consider a Riemannian Manifold $(M,g)$, we call $\nabla: TM \times TM \rightarrow TM$ a linear connection if

- $\nabla_{f U} V=f \nabla_U V$,
-  $\nabla_U(V+W)=\nabla_U V+\nabla_U W$,
-  $\nabla_U(f V)=U(f) V+f \nabla_U V$

there may be many linear connections, but there is only one linear connection which has

- $\nabla g(U, V)=g(\nabla_W U, V)+g(U, \nabla_W V)$
- $\nabla_U V-\nabla_V U=[U, V]$

where $[U,V]$ is the commutator operator $[\cdot,\cdot]:TM \times TM \rightarrow TM$ that is defined as $[U, V]=U V-V U$, it can be proven that the commutator has the following local expression

$$[U, V]^i=U\left(V^i\right)-V\left(U^i\right)=\sum_{j=1}^n\left(e_j\left(V^i\right) U^j-e_j\left(U^i\right) V^j\right)$$
where the $e_j$ are basis vectors of a local tangent space of the given manifold.

In case we have such a connection $\nabla$ which has the properties from $(1)-(5)$ it can be proven that this connection exists and is unique we call such connection a **Levi-Civita connection** on $(M,g)$ .

To get a local expression for a general manifold of the Levi-Civita connection we use the definition of the Christopher symbols of the given implicitly by $\nabla_i \mathrm{e}_j=\Gamma_{i j}^k \mathrm{e}_k$ and by using the following deduction we arrive at

$$
\begin{aligned}
\nabla_X Y & =\nabla_{X^j \partial_j}\left(Y^k \partial_k\right) \\
& =X^j \nabla_j\left(Y^k \partial_k\right) \\
& =X^j\left(\partial_j\left(Y^k\right) \partial_k+Y^k \nabla_j \partial_k\right) \\
& =X^j\left(\partial_j\left(Y^k\right) \partial_k+Y^k \Gamma_{j k}^l \partial_l\right) \\
& =X^j\left(\partial_j\left(Y^l\right)+Y^k \Gamma_{j k}^l\right) \partial_l
\end{aligned}
$$


where we use the notation convention $\partial_{j}= e_j$ for the basis vectors of the tangent space.

##### Remark
We should think of the Levi-Civita $\nabla_{U} V$ connection as way to measure the change of the vector field $V$ in the direction of the vector field $U$ which is itself another vector field.


## Submanifolds

To start this chapter we will need a lemma and a small definition.
We say that a subspace $W \subset V$ is non-degenerate if $g|_{W \times W}$ is non-degenerate.

With the previous definition clear we get from linear algebra that

The following are equivalent.
-  $W \subset V$ is non-degenerate.
-  $V=W \oplus W^{\perp}$.
-  $W^{\perp}$ is non-degenerate.

Let $\mathcal{M}$ and $\mathcal{S}$ be two manifolds, such that $\mathcal{S} \subset \mathcal{M}$ and $\mathcal{S}$ is endowed with the induced topology and differentiability structure from $\mathcal{M}$. Then any Riemannian metric $g$ on $\mathcal{M}$ induces a Riemannian structure on $\mathcal{S}$ as
$$
h(U, V)=g_{\mid \mathcal{S}}(U, V),
$$

where $U, V$ are vector fields on $\mathcal{S}$ and $h=g_{\mid \mathcal{S}}$ is the restriction of $g$ on vector fields of $\mathcal{S}$,  we say that $(\mathcal{S}, h)$ becomes a Riemannian submanifold of $(\mathcal{M}, g)$.

We can with some reasoning decompose the tangent space of $M$ with only the tangent space of $S$ be seeing that $T_{p}S \subseteq T_{p}M$ is a non-degenerate space by definition of metric and so we have by the lemma above that '
$$
T_p M=T_p S \oplus\left(T_p M\right)^{\perp}
$$
where $\oplus$ defines the a direct sum of two vector spaces.

## Second fundamental form

Let $\mathcal{S}$ be a submanifold of the Riemannian manifold $(\mathcal{M}, g)$ and denote by $\nabla$ the Levi-Civita connection on $(\mathcal{M}, g)$. 
Then for any two vector fields $U$ and $V$ on the submanifold $\mathcal{S}$ the vector field $\nabla_U V$ is not necessarily a vector field on $\mathcal{S}$. 
To put mathematically this concepts we say that $\left(\nabla_U V\right)_p$ follows the orthogonal decomposition:
$$
\left(\nabla_U V\right)_p=\left(\nabla_U V\right)_p^{\|}+\left(\nabla_U V\right)_p^{\perp}
$$
with $\left(\nabla_U V\right)_p^{\|} \in T_p \mathcal{S}$ and $\left(\nabla_U V\right)_p^{\perp} \in \left(T_p M\right)^{\perp}$ as we justified in the last section.

The second fundamental of the submanifold $S$ is defined by 
$$L(U,V) = (\nabla_{U}V)^\perp$$ for any vector fields $U,V$ in $S$

It can be proven as a consequence of the Levi-Civita connection definition that if we let $U, V, W$ be arbitrary vector fields on $\mathcal{S}$, then the second fundamental form satisfies the following properties:
-  $L$ is symmetric, $L(U, V)=L(V, U)$;
-  $L$ is bilinear: $L(U+W, V)=L(U, V)+L(W, V)$;
-  $L\left(f_1 U, f_2 V\right)=f_1 f_2 L(U, V)$ for any two differentiable functions $f_1$ and $f_2$ on $\mathcal{S}$.



## Mean Curvature Vector field

Picture this: you have a submanifold, which we'll call $(\mathcal{S}, h)$, cosily tucked into a larger Riemannian manifold we'll denote as $(\mathcal{M}, g)$. The trick here is that our submanifold takes its metric directly from the "parent" manifold, $h=g_{\mid \mathcal{S}}$.

Here's the fun part: choose a point, any point! 
As long as it belongs to our submanifold $\mathcal{S}$, we're golden. For ease, let's say it's point $p$. Now, imagine the tangent space at this point, $T_p \mathcal{S}$. We're going to set up a vector basis there, with a crew of vectors $\left\{T_1, \ldots, T_m\right\}$ ready for action. 
Now, the term $L_{i j}=L\left(T_i, T_j\right)=(\nabla_{T_{i}}{T_{j}})^{\perp}$ you see? That's simply a normal vector to $\mathcal{S}$ - each of them is, for any $1 \leq i, j \leq m$.
That's because $L_{i j} \in \left(T_p M\right)^{\perp}$. 

Moving on, we have these $h_{i j}=h\left(T_i, T_j\right)$ guys - they're the coefficients of the Riemannian metric on our submanifold, and their inverse matrix has coefficients we'll conveniently label $h^{i j}$.

Now, this is where things get even more interesting. We're going to define the mean curvature vector at our chosen point. It's like a sort of "contract" involving our previous players, expressed like this:
$$
H_p=\sum_{i, j} h^{i j}(p) L_{i j}
$$
And guess what? It belongs to $\left(T_p M\right)^{\perp}$. More importantly, if you think about it as a mapping from point $p$ to $H_p$, it defines this awesome entity called the mean curvature vector field of $\mathcal{S}$, which has the cool property of being normal to $\mathcal{S}$ at every single point, note that $H_{p}$ is a vector field! 

Now, if you fancy a simpler life, you could choose to work with an orthonormal basis for the tangent space at $p$ call it $\set{E_1,\dots,E_n}$ instead of just any old basis.

This means that $h\left(E_i, E_j\right)=\delta_{i j}$, and you can express the mean curvature vector at point $p$ as:
$$
H_p=\sum_{i, j} \delta_{i j} L\left(E_i, E_j\right)=\sum_{i=1}^m L\left(E_i, E_i\right) .
$$
Remember, though, that the mean curvature vector field depends on the second fundamental form, making it an extrinsic notion. But hey, that's just the way the cookie crumbles in the amazing world of Riemannian manifolds!

You should probably be wondering why would we bother think about this previous constructions, well turns out that they are very important to study the notion of curvature which it is very complex in differential geometry and has many interesting angles where it can be tackled.

Let's dive into the magical world of manifold curvature, and get chummy with two types of extrinsic curvatures of submanifolds: the second fundamental form and the mean curvature. These two aren't just there to look pretty – they're actually pretty good at telling us some really important stuff about the curvature of our submanifolds. 

These concepts - the second fundamental form and mean curvature - aren't just fun facts. They're actually super useful tools that will come in handy when we get to the topic of regularization.

## Relation to neural networks

The reader might have inquired what is the relation between the differential geometry concepts presented so far and neural networks. This section briefly discusses this relation, while the later sections will present a more detailed analysis.

The role of a given neural network is to approximate a certain target function $z$.
We assume that $z$ is an element of a target manifold, $\mathcal{M}$, such as the manifold of continuous functions on $[0,1]$. 
The output $y$ of the neural network is parametrized by $\theta=(w, b)$, the weighs and biases of the network. This way, the output $y$ belongs to an output manifold, $\mathcal{S}$, which is supposed to be a submanifold of the target manifold, $\mathcal{M}$.
The dimension of the submanifold $\mathcal{S}$ is equal to the number of network weights and biases, while the dimension of $\mathcal{M}$ in this case is infinite.

Lets see a very important example that illustrates the kind of manifolds that we are interested.

#### Example
The target manifold in this case can be chosen to be the space $\mathcal{M}=\mathcal{C}[0,1]$.
Consider the **logistic function** as an activation function $\sigma$  in particular it satisfies the following differential equation 
$$\sigma' = \sigma(1-\sigma)$$
The manifold of outputs
$$
\mathcal{S}=\left\{\sigma\left(w^T \mathbf{x}+b\right) ; w \in \mathbb{R}^n, b \in \mathbb{R}\right\}
$$
is an $(n+1)$-dimensional submanifold of $\mathcal{M}$. At each point $y \in \mathcal{S}$ the tangent space $T_p \mathcal{S}$ is spanned by linear combinations of the functions which can deduced from $(1)$ where the parametrization is given by $\phi(w,b)=\sigma\left(w^T \mathbf{x}+b\right)$ and so we have as consequence the following tangent basis vectors
$$
\left\{y(1-y), y(1-y) x_1, \ldots, y(1-y) x_n\right\} .
$$
The submanifold $\mathcal{S}$ can be seen as an $(n+1)$-dimensional hypersurface inside the space of real-valued continuous functions $\mathcal{M}=\mathcal{C}([0,1])$. 

In the case of one sigmoid neuron the target space $\mathcal{M}$ is not well approximated by $\mathcal{S}$ given the diversity of continuous functions that exist, to approximate better this function we need more neurons and consequently more parameters and a bigger dimension of $\mathcal{S}$.

Alrighty then, time to dive into the intricate world of neural networks. So, you know those little information-processing units we call neurons, right? Well, when you start piling them up in the network, you're not just making things busier. Each neuron you add nudges up the number of parameters, and this, in turn, boosts the dimensionality of our approximation manifold, which we'll call $\mathcal{S}$ for simplicity's sake.

So, what's the grand plan here? Imagine having a target in mind, say an element $f \in \mathcal{M}$ in the target space. Now, let's say you've also got a fixed $\epsilon>0$. The hope is that you'll be able to create a network that, with the right number of neurons (and thus high enough dimension), will shape $\mathcal{S}$ in such a way that $\operatorname{dist}(f, \mathcal{S})<\epsilon$.

And how do we measure this distance? Well, we use this fancy formula:
$$
\operatorname{dist}(f, \mathcal{S})=\inf _{s \in \mathcal{S}} \max _{x \in[0,1]}|f(x)-s(x)| .
$$

Pretty simple, right? But there's a catch. In an ideal world, you'd keep adding neurons until you achieve your desired approximation. However, the cruel reality is that neurons aren't unlimited, computational costs are very prevalent in this world.
This sets up a pretty interesting challenge: **how do you maximize the dimension of $\mathcal{S}$ while not being able to add an infinite number of neurons?**

## The Parameter space

We consider now a neural network with $L-1$ hidden layers (the layers 0 and $L$ are reserved for the input and output layers, respectively). As usual, we denote by $d^{(\ell)}$ the number of neurons in the $\ell$ th layer. For simplicity reasons, we choose $d^{(0)}=d^{(L)}=1$. Since the number of hidden neurons is equal to $N$, we have

$$
\sum_{\ell=1}^{L-1} d^{(\ell)}=N \tag{2}
$$

Imagine you're an architect, and you've been handed the task of designing the most colossal and intricate castle. Your castle is special - it's made of building blocks called "neurons", and you can arrange them in multiple layers.

Now, think of the number of neurons in each layer as $d^{(\ell)}$ where $\ell$ represents the layer number. Layer 1 might have 100 neurons, layer 2 might have 200, and so on. The layers are connected by magical bridges known as "weights." The number of these magical bridges between layer $\ell-1$ and layer $\ell$ is like multiplying the number of neurons in each of those layers, $d^{(\ell-1)} \times d^{(\ell)}$. These weights help the information flow through the castle from one layer to another.

Additionally, each neuron has a special elf called a "bias" living inside. These elves tweak and tune the information as it passes through. There is one elf in each neuron, so if there are $N$ hidden neurons, there are $N$ biases.

So, how gigantic can we make this castle? The total strength and complexity of your castle is given by the sum of all magical bridges (weights) and the number of elves (biases). Mathematically, that's:

$$
d^{(0)} d^{(1)}+d^{(1)} d^{(2)}+\cdots+d^{(\ell-1)} d^{(\ell)}+\cdots+d^{(L-1)} d^{(L)}+N .
$$

Now, here’s the quest: You have to figure out how many layers ($L$) your castle should have, and how many neurons ($d^{(\ell)}$) should be in each of these layers, so that your castle is at its mightiest, i.e., the expression above reaches its peak!

But beware, an ancient spell $(2)$ limits the power you can unleash. So, put on your wizard hat and calculate wisely to build the grandest castle (neural network) the realm has ever seen!

Imagine you are an artist, and your canvas is a large rectangle, let's call it $\mathcal{R}$. You've been given a set of colorful building blocks, each representing a layer of neurons in a neural network. You get to create an amazing mosaic within this rectangle using smaller rectangles made of your building blocks.

Each of the smaller rectangles represents the connection between two layers in a neural network. The area of these rectangles is represented by $d^{(\ell-1)} d^{(\ell)}$. It's like combining the powers of two adjacent layers of neurons!

Now picture this: you start with a rectangle made of building blocks with dimensions $d^{(0)} \times d^{(1)}$. This is your first piece of the mosaic. Then, you keep adding more pieces to your artwork, each new rectangle having dimensions $d^{(\ell-1)} \times d^{(\ell)}$. As you add these rectangles, imagine them fitting together like puzzle pieces, take this image as an inspiration

![[Screenshot 2023-07-07 171549.png|300]]

This image was taken from Calin, O. (2020) _Deep Learning Architectures_, _Springer series in the data sciences_. Springer International Publishing.

Now, here's the twist: the longer sides of the even-numbered rectangles are standing tall, while the longer sides of the odd-numbered rectangles are lying flat. Your mosaic within rectangle $\mathcal{R}$ is taking a captivating form!

The width of your main canvas, $\mathcal{R}$, is equal to the sum of the dimensions of the odd-numbered rectangles - $d^{(1)}+d^{(3)}+\cdots$, and the height is the sum of the dimensions of the even-numbered ones - $d^{(0)}+d^{(2)}+\cdots$.

However, there's an ancient spell, constraint $(2)$, that bounds your creativity. This spell dictates that the sum of the dimensions (width and height) of your canvas $\mathcal{R}$ must be constant, equal to $N$.

Your challenge, as the artist, is to arrange these rectangles within $\mathcal{R}$ in such a way that the combined area of all the smaller rectangles is maximized, while still abiding by the ancient spell.

A **combinatorial argument** shows that the optimal construction occurs only when we have $2$ hidden layers.

## Optimal Parameters Values

Let's consider a training dataset composed of pairs $\left\{\left(x_1, z_1\right),\left(x_2, z_2\right), \ldots,\left(x_n, z_n\right)\right\}$. 
Here, for each input $x_i$, there is a corresponding one-dimensional output $y_i$ from the network, where $i$ ranges from 1 to $n$.
The output $y_i$ is a function of the parameter vector $\theta$, which belongs to $\mathbb{R}^r$, i.e., $y_i = y_i(\theta)$. 

Consequently, the vector $\mathbf{y}^T$, which is composed of the outputs $\left(y_1, \ldots, y_n\right)$, resides in $\mathbb{R}^n$ and is parameterized by $\theta$. 
This vector defines a manifold $\mathcal{S}$ within $\mathbb{R}^n$, which has a dimension of $r$. Specifically, this manifold $\mathcal{S}$ can be visualized as an $r$-dimensional surface within the n-dimensional space $\mathbb{R}^n$.

The goal of training the network is to find the best set of parameters, denoted as $\theta^*$, such that the distance between the vector $\mathbf{z}^T$ (composed of $\left(z_1, \ldots, z_n\right)$) and the manifold $\mathcal{S}$ is minimized. 
This can be mathematically represented as:
$$
\theta^*=\arg \min _\theta \operatorname{dist}(\mathbf{z}, \mathcal{S})=\arg \min _\theta\|\mathbf{z}-\mathbf{y}(\theta)\|,
$$
where the distance is calculated using the Euclidean metric.
In geometric terms, this means that the vector $\mathbf{y}\left(\theta^*\right)$ is the orthogonal projection of $\mathbf{z}$ onto the manifold $\mathcal{S}$. 

### Example

Let’s unravel the intricacies of neural network architectures with the legendary MNIST dataset in the spotlight.
This dataset, with its 55,000 training examples, each featuring a flattened 784-dimensional input vector ($28 \times 28$ image) and a 10-dimensional output vector (representing the 10 digit classes), offers an intriguing playground for our mathematical explorations.

*Contextualizing the Manifold:* Consider the output manifold $\mathcal{S}$, which resides in the colossal numerical space $\mathbb{R}^{550,000}$ (resulting from $55,000 \times 10$). The dimensionality of this manifold is key to understanding the behaviour of different neural network architectures.

*Architectures Under Examination:* We’ll analyse the dimensions of $\mathcal{S}$ for two distinct feedforward neural network architectures:
1. *Single Hidden Layer:* (784-500-10) - 500 neurons in one hidden layer.
2. *Double Hidden Layers:* (784-250-250-10) - 250 neurons in each of the two hidden layers.

*Dimensionality Dissected:*
- In the *single hidden layer* architecture, the dimension of the output manifold $\mathcal{S}$ is $r = 784 \times 500 + 500 \times 10 + 500 = 397,500$. This is constituted by 784 weights from the input to the hidden layer, 500 biases, and $500 \times 10$ weights from the hidden layer to the output. The network exhibits an impressive accuracy of approximately 97.2%, with a test error of about 1.49, after empirical testing.
- Moving on to the *double hidden layers* architecture, the dimension of the output manifold drops to $r = 784 \times 250 + 250 \times 250 + 250 \times 10 + 500 = 261,500$. With this configuration, the network achieves an accuracy of 96.5%, which is slightly lower than the single hidden layer network, and a higher test error, after empirical testing.

*Optimization Alchemy:* These numerical marvels are not mere coincidences; they are the result of careful experimentation using 4,000 iterations and a batch size of 40. The Adam optimization algorithm, which is known for adaptively adjusting the learning rate, played a pivotal role. The cost function, which is the sum of squares errors, guided our optimization to seek minimal distances.

*Conclusion:* Through this examination, we witness the intimate relationship between the dimensions of output manifolds and the efficacy of neural networks. It's a meticulous balance - understanding the mathematical structures behind these architectures is paramount to harnessing their full potential. Let this serve as a testament to the power and elegance of mathematics in neural networks! 


## The Metric structure

*The Metric Odyssey in Manifold $\mathcal{S}$:* Let's embark on an exquisite geometrical journey to bestow the manifold $\mathcal{S}$ with a structure that transcends the ordinary – a Riemannian metric. This metric will be our divine instrument for measuring distances between points and the angles between the ethereal tangent vectors in $\mathcal{S}$.

*The Sublimity of $\mathcal{S}$:* Being a submanifold of the illustrious $\mathbb{R}^n$, with dimension $r$, $\mathcal{S}$ is graced with the natural metric inherited from the Euclidean grace of $\mathbb{R}^n$. Let $\theta_i$ represent the alchemy of network parameters, be it weights or biases. Our journey begins with the construction of the basic tangent vector fields to $\mathcal{S}$, bestowed by the partial derivatives with respect to the coordinates $\theta_i$.

$$
\xi_i=\frac{\partial \mathbf{y}}{\partial \theta_i}=\left(\frac{\partial y_1}{\partial \theta_i}, \ldots, \frac{\partial y_n}{\partial \theta_i}\right), \quad 1 \leq i \leq r.
$$

*The Tangent Space – A Tapestry of Vectors:* The tangent space at a point $\mathbf{y}$ in $\mathcal{S}$, denoted by $T_{\mathbf{y}} \mathcal{S}$, is a linear space woven by the threads of all basic tangent vectors at that point. This space thrives when $\mathcal{S}$ is a smooth manifold, maintaining a constant dimension $r$ at each point $\mathbf{y} \in \mathcal{S}$. The maximal rank condition encapsulates this constancy elegantly:
$$
\operatorname{rank}\left(\frac{\partial \mathbf{y}}{\partial \theta_i}\right)_i=r,
$$
asserting that the basic tangent vector fields are guardians of linear independence.

*Where Smoothness Reigns:* With the maximal rank condition, we ensure that $\mathcal{S}$ is as smooth as the calmest sea, devoid of any corners or cusps. Now, imagine a tangent vector $v$ at $\mathbf{y}$, dancing in the tangent space $T_{\mathbf{y}} \mathcal{S}$. It is defined through an elegant linear combination:
$$
v=\sum_{i=1}^r v_i \frac{\partial \mathbf{y}}{\partial \theta_i},
$$
where $v_i=v_i(\theta)$ are the harmonic components of $v$.

*The First Fundamental Form – A Metric Symphony:* The crowning jewel of our odyssey is the first fundamental form. It provides the natural metric structure of $\mathcal{S}$ with coefficients that sing the song of the inner product:

$$
g_{i j}(\mathbf{y})=\left\langle\xi_i, \xi_j\right\rangle= \sum_{k, l} g_{k l} (\mathrm{~d} x^k \otimes \mathrm{d} x^l )(\xi_i,\xi_j) =  \left(\frac{\partial \mathbf{y}}{\partial \theta_i}\right)^T \frac{\partial \mathbf{y}}{\partial \theta_j}=\sum_{k=1}^n \frac{\partial y_k}{\partial \theta_i} \frac{\partial y_k}{\partial \theta_j}.
$$

The second equality uses the tensor algebra definition of the metric tensor to compute the components only using local information, to further refer check [Riemannian manifold - Wikipedia](https://en.wikipedia.org/wiki/Riemannian_manifold)

And thus, with the first fundamental form, our manifold $\mathcal{S}$ is adorned with a Riemannian metric, and our geometric odyssey reaches its crescendo. 

With the first fundamental form defined we can start to make measures about distance and lengths, we will now measure the lengths of the vectors 

### Lengths of Vectors

Consider now the tangent vector tangent to the manifold $\mathcal{S}$ given by 

$$
v=\sum_{i=1}^r v_i \frac{\partial \mathbf{y}}{\partial \theta_i}
$$

by using the definition of metric and the upper sections we have that
$$
\begin{aligned}
\|v\|_g^2 & =\sum_{i, j} v_i v_j g_{i j}=\sum_{i, j} v_i v_j \sum_{k=1}^n \frac{\partial y_k}{\partial \theta_i} \frac{\partial y_k}{\partial \theta_j} \\
& =\sum_{k=1}^n\left(\sum_i v_i \frac{\partial y_k}{\partial \theta_i}\right)\left(\sum_j v_j \frac{\partial y_k}{\partial \theta_j}\right)=\sum_{k=1}^n\left\langle v, e_k\right\rangle^2 \\
& =\|v\|_{E u}^2 .
\end{aligned}
$$

Therefore the intrinsic and extrinsic way of measuring length is equal no matter the method..

### Lengths of curves

We will study how lengths of curves in manifolds can be used to study Hyperparameters on Neural Networks

Let's envision a scenario where the weights and biases of a neural network are tied to an additional variable, denoted as $s$. 
This variable might be time or it could be a specific hyperparameter within the network. In this context, we can write $\theta_i=\theta(s), 1 \leq i \leq r$, thus $c(s)=\mathbf{y}(\theta(s))$ defines a curve in the manifold space $\mathcal{S}$. 
In essence, this means that the variation of a network hyperparameter can be viewed as the tracing of a curve within this manifold.

The next part of our exploration involves the length of the curve $c(s)$ when $s$ ranges between two values $a$ and $b$. 
The intrinsic definition of this curve length can be expressed via the integral

$$
L(c)=\int_a^b\|\dot{c}(s)\| d s=\int_a^b \sum_{i, j} \dot{c}_i(s) \dot{c}_j(s) g_{i j}(c(s)) d s
$$

Here, $\dot{c}(s)$ symbolizes the tangent vector to the curve. 
Making use of the chain rule, we can further express the derivative of $c(s)$ as

$$
\dot{c}(s)=\frac{d}{d s} c(s)=\frac{d}{d s} \mathbf{y}(\theta(s))=\sum_i \frac{\partial \mathbf{y}}{\partial \theta_i} \frac{d \theta_i}{d s}=\left\langle\nabla_\theta \mathbf{y}, \dot{\theta}(s)\right\rangle \tag{3}
$$

Through these mathematical transformations, we've essentially translated the changes in the neural network parameters into the geometrical notion of curve length within a manifold space. This serves as a powerful visualization tool for understanding the inner workings of neural networks. How can we use this to understand the fine-tunning process ?

The answer is in geodesics and we will explore them now with the previous concepts that we wrote above and finish this exposition.

There are instances where we seek the shortest curve, or path, connecting two specific points on our manifold $\mathcal{S}$. For a flat space like $\mathbb{R}^n$, this shortest path is simply a straight line. However, when we consider a more complex structure such as the manifold $\mathcal{S}$, the quest for the shortest path is not as straightforward. The shortest paths on such a structure are referred to as geodesics.

Geodesics serve a key purpose in neural network optimization. For instance, we may be interested in finding the shortest path between an initial point, $\mathbf{y}\left(\theta^0\right)$, and the optimal point, $\mathbf{y}\left(\theta^*\right)$. This optimal point represents the orthogonal projection of a target point $\mathbf{z}$ onto the manifold $\mathcal{S}$. 

In the language of neural networks, traversing this shortest curve is equivalent to the most efficient fine-tuning of network parameters, given that any such tuning maps to a curve on the manifold.
This geometric interpretation of network optimization can provide deeper insights into the process and potentially lead to more efficient strategies for parameter adjustment.

We will now get into the analytical aspect of this phenomena to find the behaviour of the optimal parameter point of the neural network.

Imagine you're adjusting parameters $\theta(s)$ in terms of $s$, and you see an initial spike in accuracy, which later tapers off to a decrease. The minimal error aligns with a certain optimal value $s^*$. From a geometric perspective, this optimal value is represented as the point on the curve $c(s)$ that is nearest to the target point $\mathbf{z}$ .

Take this image as model in your mind.

![[Screenshot 2023-07-07 160357.png|300]]

This image was taken from Calin, O. (2020) _Deep Learning Architectures_, _Springer series in the data sciences_. Springer International Publishing.

This proximity condition occurs when the vector stretching from the curve point to the target, $\overrightarrow{\mathbf{z} c(s)}$, is orthogonal to the tangent vector $\dot{c}(s)$ at that point.
This relationship can be formally expressed as:
$$
(\mathbf{z}-c(s))^T \dot{c}(s)=0 .
$$
Assuming the parameter $s$ is altered such that the squared magnitude of the rate of change, $\|\dot{c}(s)\|^2$, remains constant, differentiating and applying the product rule will result in $c(h)^T \dot{c}(h)=0$. Consequently, the previous equation transforms into $\mathbf{z}^T \dot{c}(h)=0$. 

Employing formula the formula $(3)$, we deduce that the optimal value $s^*$ must satisfy the equation
$$
\left\langle\nabla_\theta\left(\mathbf{z}^T \mathbf{y}\left(s^*\right)\right), \dot{\theta}\left(s^*\right)\right\rangle=0
$$
This geometric framework offers an intuitive understanding of how the optimal parameters for neural networks can be determined, enabling more effective tuning and potentially enhancing model performance.

## Future Considerations

This set of notes is ending here, however there are still many unexplored questions that could be explored regarding this topic, this sections opens up for people who want to take this concepts further or that are just curious where this exposition was leading too.

### Regularization
There are plenty of questions when it comes to regularization in fine-tuning neural networks, given that the learning process can be seen as a path in the submanifold of learning $\mathcal{S}$ the local properties around optimal points and points around the path more generally can heavily affect the learning process, making it more slow or even inaccurate in some cases, there is plenty of mathematics involved when to it comes to this questions and lots of local geometry questions that are heavily mathematical based.

### Differential Statistics and Neuromanifolds
Secondly, machine learning by its nature is very statistical, however we didn't say anything about statistics, this link has been studied by some mathematicians such as Fischer, the field of differential statistics originates the so called **statistical manifold** of which the ones we considered here are a particular case, seeing this manifolds as objects where statistical properties can be applied originate great mathematical content, such an example is the Fischer information matrix, that serves its purpose to study the influence of statistical variance in the manifolds, such properties help us understand better the learning process associate with them , statistical manifolds associated with ANN are called **Neuromanifolds** and these are somewhat recent objects that are being study fairly recently.

#### Bibliography
This exposition was heavily based in Calin, however other references were taken in consideration when it came to a more conceptual understanding of the mathematical objects being explained here.

1. Calin, O. (2020) _Deep Learning Architectures_, _Springer series in the data sciences_. Springer International Publishing
2. [Riemannian manifold - Wikipedia](https://en.wikipedia.org/wiki/Riemannian_manifold)
3. Lee, J. D. (2012). Introduction to Smooth Manifolds. In _Springer eBooks
4. Lee, J. D. (2011). Introduction to Topological Manifolds. In _Graduate texts in mathematics_. Springer Nature
5. Chikuse, Y. (2003). Statistics on Special Manifolds. In _Springer eBooks

