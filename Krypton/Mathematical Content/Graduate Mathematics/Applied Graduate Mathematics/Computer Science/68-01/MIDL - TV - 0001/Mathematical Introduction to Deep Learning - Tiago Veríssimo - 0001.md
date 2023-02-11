### Author : [[Tiago Veríssimo 0001]]

# Abstract


# Activation Functions

In this section we will be dealing with activation functions, this functions are responsible to simulate the "firing" behaviour of neurons and have a great impact in the learning of neural networks depending on the problem in question. 

## Examples of Activations functions

We now present a great deal of diverse activation functions.

### Family of Linear functions

**Linear Function:**
This is the simplest class of activation functions and this consists only of function of the type $f(x)=kx$ with $k > 0$ constant and in this case in particular we have that $f'(x)=k$.
Here the constant slope is used to model the firing rate of a neuron.
This type of functions is usually used in a **multilayer neural network**.

### Step Functions

**Step Functions:**
This biologically inspired type of activation functions exhibit an upward jump that simplistically models a neuron activation.

We have two functions types of this activations functions:

**Heaviside function**
This is function is given by 

$$H(x) =
\begin{cases}
0, \quad x < 0  \\
1, \quad x \geq 0
\end{cases}
$$

and it pretends to simulate the behavoiour of a function that fires only when we have values of $x$ greater or equal than $0$ 
This function is not diferentiable, because it is not continous, however we have that there exists a concept called **generalised derivative** that wants to mimic in some way the concept of a derivative, in this case we have that

$$
\delta(x) = H'(x) = \begin{cases}
0, \quad x \ne 0 \\
+ \infty, \quad x = 0
\end{cases}
$$

which has the special property that $\int^{}_{\mathbb{R}}\delta(x) dx=1$ 

**Bipolar Step Function** 

This function is given by 
$$
S(x) = \begin{cases}
-1, \quad x <0 \\
1, \quad x \geq 0
\end{cases}
$$
and is sort of an alterned version of the **Heaviside Function** because $S(x)=2H(x)-1$ and from here we have that $S'(x)=2H'(x)=2 \delta(x)$ 


### Hockey-Stick Functions

This class of this functions has graphs that resemble a hockey stick or an increasing L-shaped curve.

**Rectified Linear Unit (ReLU)** 

In this case the activation activates only after $x \geq 0$ and is defined as

$$
ReLU(x)= x H(x) = \max \set{x,0} = \begin{cases}
0, \quad x< 0 \\
x, \quad x \geq 1
\end{cases}
$$

and the derivative $ReLu'(x) = H(x)$

Neural networks with $ReLU$ activation function tend to learn several times faster than a similar network with saturating activation functions, such as logistic or hyperbolic tangent.

**Parametric Rectified Linear Unit (PReLU)**

In this case the activation function is piecewise linear and is defined as

$$
PReLU(\alpha,x) = \begin{cases}
\alpha x \quad x< 0  \\
x, \quad x \geq0
\end{cases}
,\quad \alpha >0
$$
Pagina 50