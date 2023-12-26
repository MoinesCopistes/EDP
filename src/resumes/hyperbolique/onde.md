## Forme Générale
$$
\large \boxed{c^{2} \phi_{xx}=\phi_{tt}}
$$
On a $\large A=c^{2}, B=0,C=-1$, ce qui donne $\large B^{2}-4AC=4c^{2}>0$ car $\large c$ est réel. L'équation d'onde est une équation ***hyperbolique***, ***homogène***, ***linéaire*** (parce qu'en général $\large c$ ne va pas dépendre de $\large \phi$ ou de ses dérivées)

## Caractéristiques

Les directions caractéristiques $(dx, dt)$ sont les solutions de $(dx)^2 = c^2 (dt)^2$. Les racines sont effectivement réelles et distinctes: $\frac{dx}{dt} = c$ et $\frac{dx}{dt} = -c$. Comme c est ici constant, les caractéristiques forment un réseau régulier de droites.

***Il faut encore une fois faire attention à d'où vient l'information pour s'assurer que le problème est bien posé.***
## Problème aux Conditions Initiales

On regarde le problème aux conditions initiales et en domaine non borné ou périodique. Les caractéristiques émanant d'un point s de $\Gamma$ ont comme équation $x - ct = s$ et $x + ct = s$. Le problème est bien posé puisque $\Gamma$ est non parallèle au réseau des caractéristiques. On doit y spécifier $\phi(s, 0) = f(s)$ et $\frac{\partial \phi}{\partial t} (s, 0) = g(s)$
On peut appliquer la méthode des caractéristiques à ce problème mais c'est vachement nul comme méthode honnêtement.
Il est plus malin de factoriser l'équation ce qui nous permet de trouver la formule d'Alembert, avec les conditions initiales : $\large \phi(x,t=0)=f(x)$ et $\large \phi_{t}(x,t=0)=g(x)$ :$$
\large \phi(x,t)=f_{1}(x+ct)+f_{2}(x-ct)=\frac{f(x+ct)+f(x-ct)}{2}+\frac{1}{2c}\int_{x-ct}^{x+ct}g(s') \, ds' 
$$
### Avec $\large c(x)$
L'équation d'onde avec $\large c = c(x)$ est
$$
\large \frac{\partial}{\partial x} \left( c \frac{\partial \phi}{\partial x} \right) - \frac{\partial^2 \phi}{\partial t^2} = 0 \quad
$$
On définira ici que $\large u = \frac{\partial}{\partial x} (c \phi)$ et $\large v = \frac{\partial \phi}{\partial t}$. On peut alors utiliser la méthode des caractéristiques pour la résoudre.
On note aussi que l'EDP peut se factoriser:
$$
\large \frac{\partial}{\partial x} (c \phi) + \frac{\partial \phi}{\partial t} = \psi \quad \text{puis} \quad \frac{\partial}{\partial x} (c \psi) - \frac{\partial \psi}{\partial t} = 0 \quad
$$

### Sous Forme de Système

$$
\large c^{2} \phi_{xx}=\phi_{tt}
$$
Soient $\large u=c\phi_{x}$ et $\large v=\phi_{t}$, qui donnent :
$$
\large \left\{ \begin{align}
c\,u_{x}-v_{t}&=0 \\
cv_{x}-u_{t}&=0
\end{align} \right. \Leftrightarrow \frac{\partial}{\partial t} \begin{pmatrix}u\\v\end{pmatrix} + \underbrace{\begin{pmatrix}
0 & -c  \\
-c & 0 
\end{pmatrix} }_{\large A}\frac{\partial}{\partial x} \begin{pmatrix}u\\v\end{pmatrix}=\begin{pmatrix}
0 \\
0
\end{pmatrix}
$$
Les valeurs propres de $\large A$ sont obtenues par annulation de déterminant de $\large A-\lambda I$ qui donne les directions caractéristiques, ici $\large c$ et $\large -c$. En annulant le déterminant de la grosse matrice on trouve finalement que $\large u-v$ est conservé le long de $\large \frac{dx}{dt}=c$ et $\large u+v$ est conservé le long de $\large \frac{dx}{dt}=-c$.

### Sous Forme de Système avec $\large c(x)$

$$
\large \frac{\partial}{\partial x} \left( c \frac{\partial \phi}{\partial x} \right) - \frac{\partial^2 \phi}{\partial t^2} = 0 \quad 
$$
Soient $\large u=c\phi_{x}$ et $\large v=\phi_{t}$, qui donnent :
$$
\large \frac{\partial}{\partial x}(cu)-v_{t}=0
$$
Et le système :
$$
\large \left\{ \begin{align}
\frac{\partial}{\partial x}(cu)-v_{t}&=0 \\
\frac{\partial}{\partial x}(cv)-u_{t}&=0
\end{align} \right. 
$$
Si $\large p=cu$ et $\large q=cv$
$$
\large \left\{ \begin{align}
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
\large k_{mn}=\frac{z_{mn}}{a}
$$

Où $\large z_{mn}$ est la $\large n^{e}$ racine de la $\large m^{e}$ fonction de Bessel de première espèce.