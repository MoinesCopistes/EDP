# Équation de Laplace
## Forme Générale 2D
$$
\phi_{xx}+\phi_{yy}=0\Leftrightarrow \nabla^{2}\phi=0
$$
Avec $A=1,B=0,C=1,R=0\Rightarrow$ ***Elliptique***. Les solution des équations des caractéristiques sont imaginaires, il n'y en a pas.

Les problèmes elliptiques doivent être résolus de manière globale: tous les points influencent tous les points! Ces problèmes sont toujours résolus sur un domaine physique $\Omega$. Si le domaine est borné, il faut donner une condition en tout point de sa frontière $\partial \Omega$ paramétrisée par $s$. On y prescrit soit la fonction $\phi(s)$ (Dirichlet), soit la dérivée normale$\frac{\partial \phi}{\partial n}(s)$ (Neumann), soit une condition mixte (Robin).

## Solutions

### Non Borné

#### Condition Initiale Sing


## Système
On définit $u=\phi_{x}$ et $v=\phi_{y}$, qui donne le système :
$$
\begin{align}
u_{x}+v_{y}&=0 \\
v_{x}-u_{y}&=0
\end{align}
$$
On obtient donc :
$$
\frac{\partial}{\partial x} \begin{pmatrix}u\\v\end{pmatrix}+\begin{pmatrix}0&1\\-1&0\end{pmatrix} \frac{\partial}{\partial y}\begin{pmatrix}u\\v\end{pmatrix}=0
$$
La matrice $A$ est :
$$
A=\begin{pmatrix}
0&1 \\
-1&0
\end{pmatrix}
$$
Et ses valeurs propres sont complexes conjugués $\lambda^{2}=-1$ et donc $\lambda_{1}=i$ et $\lambda_{2}=-i$. Ce système est donc elliptique. Il n'y a pas de direction caractéristique, ni de méthode des caractéristiques.