# Équation d'Onde

## Forme Générale

$$
\boxed{c^{2} \phi_{xx}=\phi_{tt}}
$$
On a $A=c^{2}, B=0,C=-1$, ce qui donne $B^{2}-4AC=4c^{2}>0$ car $c$ est réel. L'équation d'onde est une équation ***hyperbolique***, ***homogène***, ***linéaire*** (parce qu'en général $c$ ne va pas dépendre de $\phi$ ou de ses dérivées)

## Caractéristiques

Les directions caractéristiques $(dx, dt)$ sont les solutions de $(dx)^2 = c^2 (dt)^2$. Les racines sont effectivement réelles et distinctes: $\frac{dx}{dt} = c$ et $\frac{dx}{dt} = -c$. Comme c est ici constant, les caractéristiques forment un réseau régulier de droites.

***Il faut encore une fois faire attention à d'où vient l'information pour s'assurer que le problème est bien posé.***
## Problème aux Conditions Initiales

On regarde le problème aux conditions initiales et en domaine non borné ou périodique. Les caractéristiques émanant d'un point s de $\Gamma$ ont comme équation $x - ct = s$ et $x + ct = s$. Le problème est bien posé puisque $\Gamma$ est non parallèle au réseau des caractéristiques. On doit y spécifier $\phi(s, 0) = f(s)$ et $\frac{\partial \phi}{\partial t} (s, 0) = g(s)$
On peut appliquer la méthode des caractéristiques à ce problème mais c'est vachement nul comme méthode honnêtement.
Il est plus malin de factoriser l'équation ce qui nous permet de trouver la formule d'Alembert, avec les conditions initiales : $\phi(x,t=0)=f(x)$ et $\phi_{t}(x,t=0)=g(x)$ :$$
\phi(x,t)=f_{1}(x+ct)+f_{2}(x-ct)=\frac{f(x+ct)+f(x-ct)}{2}+\frac{1}{2c}\int_{x-ct}^{x+ct}g(s') \, ds' 
$$
### Avec $c(x)$
L'équation d'onde avec $c = c(x)$ est
$$
\frac{\partial}{\partial x} \left( c \frac{\partial \phi}{\partial x} \right) - \frac{\partial^2 \phi}{\partial t^2} = 0 \quad
$$
On définira ici que $u = \frac{\partial}{\partial x} (c \phi)$ et $v = \frac{\partial \phi}{\partial t}$. On peut alors utiliser la méthode des caractéristiques pour la résoudre.
On note aussi que l'EDP peut se factoriser:
$$
\frac{\partial}{\partial x} (c \phi) + \frac{\partial \phi}{\partial t} = \psi \quad \text{puis} \quad \frac{\partial}{\partial x} (c \psi) - \frac{\partial \psi}{\partial t} = 0 \quad
$$

### Sous Forme de Système

$$
c^{2} \phi_{xx}=\phi_{tt}
$$
Soient $u=c\phi_{x}$ et $v=\phi_{t}$, qui donnent :
$$
\left\{ \begin{align}
c\,u_{x}-v_{t}&=0 \\
cv_{x}-u_{t}&=0
\end{align} \right. \Leftrightarrow \frac{\partial}{\partial t} \begin{pmatrix}u\\v\end{pmatrix} + \underbrace{\begin{pmatrix}
0 & -c  \\
-c & 0 
\end{pmatrix} }_{A}\frac{\partial}{\partial x} \begin{pmatrix}u\\v\end{pmatrix}=\begin{pmatrix}
0 \\
0
\end{pmatrix}
$$
Les valeurs propres de $A$ sont obtenues par annulation de déterminant de $A-\lambda I$ qui donne les directions caractéristiques, ici $c$ et $-c$. En annulant le déterminant de la grosse matrice on trouve finalement que $u-v$ est conservé le long de $\frac{dx}{dt}=c$ et $u+v$ est conservé le long de $\frac{dx}{dt}=-c$.

### Sous Forme de Système avec $c(x)$

$$
\frac{\partial}{\partial x} \left( c \frac{\partial \phi}{\partial x} \right) - \frac{\partial^2 \phi}{\partial t^2} = 0 \quad 
$$
Soient $u=c\phi_{x}$ et $v=\phi_{t}$, qui donnent :
$$
\frac{\partial}{\partial x}(cu)-v_{t}=0
$$
Et le système :
$$
\left\{ \begin{align}
\frac{\partial}{\partial x}(cu)-v_{t}&=0 \\
\frac{\partial}{\partial x}(cv)-u_{t}&=0
\end{align} \right. 
$$
Si $p=cu$ et $q=cv$
$$
\left\{ \begin{align}
c\,p_{x}-q_{t}&=0 \\
c\,q_{x}-p_{t}&=0
\end{align} \right. \Leftrightarrow \frac{\partial}{\partial t} \begin{pmatrix}p\\q\end{pmatrix} + \begin{pmatrix}
0 & -c  \\
-c & 0 
\end{pmatrix}\frac{\partial}{\partial x} \begin{pmatrix}p\\q\end{pmatrix}=\begin{pmatrix}
0 \\
0
\end{pmatrix}
$$






## Domaine Circulaire

Le nombre d'onde d'un des modes d'une membrane circulaire est donnée par :

$$
k_{mn}=\frac{z_{mn}}{a}
$$

Où $z_{mn}$ est la $n^{e}$ racine de la $m^{e}$ fonction de Bessel de première espèce.