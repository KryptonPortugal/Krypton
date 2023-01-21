# Author : [[Tiago Veríssimo 0001]]

#### Motivations
There are plenty of motivations to study diferential geometry, here are some:
- Beautifull mathematical subject
- Aplications in industry (Deep Learning, Package Development, ...)
- Aplications in Pure Sciences (Theoretical Physics, Biology, ...)

#### Main ideas
Diferential geometry is the study of a very special object called **manifold**, typically denoted by $M$, this object can be various things such as a sphere $S^2$ or a torus $T^2$ or even a cube.
However, in this notes we study only a very special type of manifold that are **smooth manifolds**, which as an intuition we can have $S^2$ which are intuitevely surfaces which are smooth, in some way related to the variation of the surface, for comparsion a cube is **not** a smooth manifold.
To study this structure, we use something called charts which are essentially a way of describing this manifold objects in a local manner using $\mathbb{R}^n$ and with this we can get some local properties of $M$ which sometimes turn to be local properties. This idea of going from the local to the global is something very much studied and this results are typically of great influence, e.g Gauss-Bonet Theorem.


## Foundations of Manifold Theory

It is of fundamental importance to the readers to be acquainted with the definition of a [[Topological Space]] which comes as

![[Topological Space]]

this will let us play with the *topus* of the objects we will study and plays a crucial role in geometry in general.

Two examples of topologies are the :

![[Trivial Topology]]

and

![[Discrete Topology]]


however we usually in this notes will work with the [[Euclidean Topology]] which comes as

![[Euclidean Topology]]

One properties that is usually usefull in manifolds is the something which we call being a [[Hausdorff Space]], this are spaces with the follwing property

![[Hausdorff Space]]


Sometimes we interested in a [[Basis]] $B \subseteq O$ of a topological space $(X,O)$.
This concept comes as

![[Basis]]

In particular we are interested when we have a countable basis $B$ of $(X,O)$ we call this spaces [[Second Coutable]], here is a formal definition.

![[Second Coutable]]

Another usefill ideia is the concept of [[Open Neighborhood]] which is defined as

![[Open Neighborhood]]

Is usefull to study topological spaces to study functions from one Topological Space to another, usually we are specially interested in studying functions like this that are continous.
We define now what is a [[Continuous Function]] in the topological sense

![[Continuous Function]]


in particular there is a very special type of continous function that are is called an **Homeomorphism**
which has very special properties

![[Homeomorphism]]


another concept yet that is usefull is the concept of [[Locally Euclidean]], this is usefull when we want to study manifolds locally 

![[Locally Euclidean]]

we will work a lot with [[Locally Euclidean]] spaces therefore we will give the definition of what is an [[Chart]]

![[Chart]]

After introducing all these topological concepts we are in a position of understanding what a [[Topological Manifold]] is

![[Topological Manifold]]

	Remark
1. If a manifold $M$ is locally euclidean in $\mathbb{R}^{n}$ we say that the manifold has dimension $n \in \mathbb{N}$ and write it as $M^{n}$

We are now interested in studying whether two charts are compatible, this notion is interesting because we want to be able to construct an object called and **atlas** which is composed by many charts  and is used to cover manifolds, however not all **charts** are compatible. We now study when are atlas compatible.

We say that we have two charts are $C^{k}$ - [[Compatible Charts]] if 

![[Compatible Charts]]

	Remarks
1. If $(U,\phi)$ is a chart of $n$ dimensions manifold $M$ we note that we can decompose $\phi$ as $\phi(x)=(\phi^{1}(x),\dots,\phi^{n}(x))$ 
2. The map $\phi_{2} \circ \phi_{1}^{-1} : \phi_{1}(U_{1}\cap U_{2}) \rightarrow \phi_{2}(U_{1} \cap U_{2})$ in this conditions is always a [[Homeomorphism]].

We now can define what an [[Atlas]] is

![[Atlas]]


With this in mind we can define [[Smooth Manifold]] as

![[Smooth Manifold]]


Note that if $M$ is a set and $\phi_{i}: U_{i} \rightarrow \phi_{i}(U_{i}) \subseteq \mathbb{R}^{n}$ with $i \in I$ are bijective we have that
- $\bigcup_{i \in I} U_{i} = M$ (Definition of [[Atlas]])
- $\phi_{i}(U_{i} \cap U_{j}) \subseteq \mathbb{R}^{n}$ for all $i,j \in I$   (Openess of the transitive maps)
- Because we have that all transitive maps are continous we can define an unique [[Topological Space]] named $(M,\tau)$ as defining $X \subseteq M$ to be open if and only if for all $i \in I$ we have $\phi_{i}(X \cap U_{i}) \subseteq \mathbb{R}^{n}$ is open in the euclidean topology.


With that topology on sight we can we can notice some usefull facts like:
- If $I$ is countable then $M$ is second countable





