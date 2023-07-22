#Tiago_Veríssimo 

## Author: Tiago Mesquita Santos Veríssimo

#### Abstract
This set of notes will be exposing the fundamental concepts needed to build upon differential geometry to get into general relativity this set of notes is made without considering the physical evolution of general relativity theory, this are purely mathematical notes that are meant to connect to further more physical notes.

We will be covering:
- Differential Geometry with no metric
- Differential Geometry with metric
- Petrov classification
- Ricci Tensor and energy-momentum tensor
- Vector fields
- Newman-Penrose Diagrams
- Groups of transformations
- Isometry and Homothety Groups
- Generation Techniques

This set of notes is meant to connect with further notes on general relativity, making this a very solid reference for people who are interested in the mathematical requisites of this theory.

##### Pre-requisites
This exposition requires the reader to have a basic understanding of:
- General Topology
- Real analysis
- Linear Algebra

## Differential Geometry with no Metric

### Differentiable Manifolds

A chart $(\mathcal{U}, \Phi)$ in $\mathcal{M}$ consists of a subset $\mathcal{U}$ of $\mathcal{M}$ together with a one-to one map $\Phi$ from $\mathcal{U}$ onto the $n$-dimensional Euclidean space $E^n$. The map $\Phi$ assigns to every point $p \in \mathcal{U}$ an $n$-tuple of real variables, the local coordinates $\left(x^1, \ldots, x^n\right)$. 

We say that two charts $(\mathcal{U}, \Phi),\left(\mathcal{U}^{\prime}, \Phi^{\prime}\right)$ are said to be compatible if the combined map $\Phi^{\prime} \circ \Phi^{-1}$ on the image $\Phi\left(\mathcal{U} \cap \mathcal{U}^{\prime}\right)$ of the overlap of $\mathcal{U}$ and $\mathcal{U}^{\prime}$ is a homeomorphism. An atlas on $\mathcal{M}$ is a collection of compatible charts $\left(\mathcal{U}_\alpha, \Phi_\alpha\right)$ such that every point of $\mathcal{M}$ lies in at least one chart neighbourhood $\mathcal{U}_\alpha$. 


An $n$-dimensional (topological) manifold consists of a space $\mathcal{M}$ together with an atlas on $\mathcal{M}$. It is a ( $C^k$ or analytic) differentiable manifold $\mathcal{M}$ if the maps $\Phi^{\prime} \circ \Phi^{-1}$ relating different charts are not just continuous but differentiable (respectively, $C^k$ or analytic). Then the coordinates are related by $n$ differentiable $\left(C^k\right.$, analytic) functions.

It happens that diffeomorphisms have special properties that make possible to assert that the Jacobian of two coordinate transformations never vanish, putting it in a rigorous way let $x \in U \subseteq \mathbb{R}^n$ and consider $\varphi$ a diffeomorphism between $\mathcal{M}$ and $\mathbb{R}^{n}$.
we have then that
$$
\varphi^{-1}(\varphi(x))=x=i d(x)
$$
Take the Jacobian on both sides and apply the chain rule on the left-hand side :
$$
D \varphi^{-1}(\varphi(x)) \cdot D \varphi(x)=I_n
$$
So $D \varphi(x)$ is invertible $\forall x \in U$.
Therefore we have in particular that $\det D\varphi \ne 0$ as a consequence we can consider transition maps $\Phi^{\prime} \circ \Phi^{-1}$ and note that their Jacobian does not vanish either because we have that 
$$
D(\Phi^{\prime} \circ \Phi^{-1}) = D\Phi^{\prime}(\Phi) \circ D\Phi^{-1}
$$
and as a consequence we have 
$$
\det D(\Phi^{\prime} \circ \Phi^{-1}) = \det D\Phi^{\prime}(\Phi) \det  D\Phi \ne 0
$$
because either $\det D\Phi^{\prime}(\Phi)$ or $\det D\Phi^{-1}$ are non-zero. We can say now that the Jacobians of the transition maps never vanish.

---
**Remark**
Usually in the literature we assume that to have a smooth manifold we have to assume the topological properties of being Hausdorff and Second Countable, indeed this properties are very much important in the development of the theory, and we will use them implicitly through our digression, to check a more rigorous approach check the references.

---

A differentiable manifold $\mathcal{M}$ is called orientable if there exists an atlas such that the Jacobian is positive throughout the overlap of any pair of charts.

If $\mathcal{M}$ and $\mathcal{N}$ are manifolds, of dimensions $m$ and $n$, respectively, the $(m+n)$-dimensional product $\mathcal{M} \times \mathcal{N}$ can be defined via the coordinate maps $\phi \times \psi$ where $\phi$ and $\psi$ are coordinates maps of $\mathcal{M}$ and $\mathcal{N}$, respectively.  

A map $\Phi: \mathcal{M} \rightarrow \mathcal{N}$ is said to be differentiable if the coordinates $\left(y^1, \ldots, y^n\right)$ on $\mathcal{V} \subset \mathcal{N}$ are differentiable functions of the coordinates $\left(x^1, \ldots, x^n\right)$ of the corresponding points in $\mathcal{U} \subset \mathcal{M}$ where $\Phi$ maps (a part of) the neighbourhood $\mathcal{U}$ into the neighbourhood $\mathcal{V}$, to put it in a more rigorous way we have to get that $\psi \circ \Phi \circ \phi^{-1}$ is a differentiable function.

If $\Phi(\mathcal{M}) \neq \mathcal{N}$, $\Phi(\mathcal{M})$ is called a submanifold of $\mathcal{N}$ : submanifolds $\mathcal{P} \subset \mathcal{N}$ of dimension $p<n$ can also be defined by the existence of charts $(\mathcal{V}, \Psi)$ in $\mathcal{N}$ such that $\mathcal{P} \cap \mathcal{V} \subset \mathbb{R}^p \times 0$ where the 0 is the zero of $\mathbb{R}^{n-p}$. 
A submanifold of dimension $n-1$ will be called a hypersurface.

A smooth curve $\gamma(t)$ in $\mathcal{M}$ is defined by a differentiable map of an interval of the real line into $\mathcal{M}$
$$
\gamma(t):-\varepsilon<t<\varepsilon \rightarrow \mathcal{M}
$$


### Tangent vectors
