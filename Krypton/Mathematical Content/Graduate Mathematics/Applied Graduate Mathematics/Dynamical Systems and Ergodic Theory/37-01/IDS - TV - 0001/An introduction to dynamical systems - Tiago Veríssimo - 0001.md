### Author : [[Tiago Veríssimo 0001]]

## Abstract
In this notes we will explore two topics:
- General Theory of Dynamical Systems
- Hyperbolic Dynamical Systems

## Preliminaires

We will begin the study of this notes by defining rigoursly what is a dynamical system, specially a [[Topological Dynamical System]] which is exacly

![[Topological Dynamical System]]

in this spaces there are some usefull structures that are of great use.
We consider now the concept of an [[Orbit of the dynamical system]] which is 

![[Orbit of the dynamical system]]


With this two concepts in mind we can already ask ourselfs a great deal of interesting questions, we consider first the question of what type of **orbits** there exists in a dynamical system $(X,T)$.

There two special kinds of orbits that we can consider:

- Periodic Orbits
- Dense Orbits

We call an **orbit** $\sigma$ in $(X,T)$ a [[Dynamical Periodic Orbit]] if 

![[Dynamical Periodic Orbit]]

and we call $\sigma$ a [[Dynamical Dense Orbit]] if we have that

![[Dynamical Dense Orbit]]

there is a very special notion in dynamical systems that is very usefull as we will se as the notes progress, this notion is what we call [[Dynamical T-invariant]] and some subsets of the [[Topological Dynamical System]] have it, we define it formally as 

![[Dynamical T-invariant]]

and we arrive at our first proposition, the fact that the [[Closure of a Dynamical Orbit is T-Invariant]] which formally stays as

![[Closure of a Dynamical Orbit is T-Invariant]]

and the proof is made here

---

### Example 1

We go for our **first example** of a dynamical system, namely consider the dynamical system where the set $X = [0,1]/\sim$  in the dynamical system $(X,T)$ where we have the continuos function $T$ is
$$
\begin{align}
T: X \rightarrow X \newline x \mapsto2x
\end{align}
$$

and the equivalence relation is defined by identifiying $0 \sim 1$ 

At first glance this might seem a bit of an easy example, however this can get very extreme, for example we will prove further in the notes that this dynamical system has

- Has a dense set
- Has positive Entropy
- Has a dense set of periodic orbits

We will from times to times comeback to this example.

We know define what is a **flow**, rigoursly we have that a [[Continuous Flow]] is

![[Continuous Flow]]


however in this notes we will be mostly interested in discrete dynamical systems and so we define a [[Discrete Flow]] as

![[Discrete Flow]]

we consider now an example of a continuous dynamical system

### Example 2

Consider the dynamical system $(\mathbb{R}^{n},X)$ defined by the set of equations
$$
\begin{cases*}
X' = f(X) \newline
X_{0}(K) = K
\end{cases*} 
$$
then we have as a [[Continuous Flow]] the function $\phi: \mathbb{R} \rightarrow \mathbb{R^n}^{\mathbb{R}^n}$ defined as

$$
\phi(t) =  X_{t}(K), \qquad \phi(0) = X_{0}(K) = K
$$

as an example we have the dynamical system $(\mathbb{R}^{2}, X)$ defined as 

$$
\begin{cases*}
x' = -y \newline
y' = x  \newline
X_{0}(K) = K
\end{cases*}, \qquad X_{t}(K) = \begin{bmatrix}
x(0)  \\ y(0) 
\end{bmatrix}
$$

and we have the [[Continuous Flow]] if we define

$$\phi(t) = X_{t}(K) = \begin{bmatrix}
x(t) \\ y(t) 
\end{bmatrix}, 

\qquad \phi(0) = X_{0}(K) =\begin{bmatrix}
x(0) \\ y(0) 
\end{bmatrix} = K

$$

in this case we have

$$
\phi(t) = X_{t}(K)= \begin{bmatrix}
x(t) \\ y(t) 
\end{bmatrix} =
\begin{bmatrix}
cos(t)x(0) - sin(t)y(0)  \\ sin(t)x(0) + cos(t)y(0) 
\end{bmatrix}
$$

## Rotations on the Circle

In this section we will study a very specific example which in $S^{1}$.

Firstly, we note that $S^{1}$ can be defined in various ways however we will consider for the sake of usefulness we will consider the representation $S^{1} \cong [0,1]/\sim$ where the equivalence relation is defined by $0 \sim 1$

From here we will define the map 

$$
\begin{align}
R_{\alpha}: S^{1} \rightarrow S^{1} \\ x \mapsto x + \alpha \mod{1}
\end{align}
$$

that wants to simulate the rotation of points in the circle.
We will now study some properties of the dynamical system $(S^{1},R_{\alpha})$ starting with the first theorem thas goes as

![[Theorem 1 -  IDS - TV 0001]]

the proof of this result can be seen down here  

![[Proof - Theorem 1 - IDS - TV 0001]]


A dynamical system $(X,f)$ is said to be [[Topological Transitive]] if we have:

![[Topological Transitive]]


and we say that $(X,f)$ is said to be [[Topological Minimal]] if we have:

![[Topological Minimal]]

