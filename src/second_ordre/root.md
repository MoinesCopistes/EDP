# Équations du Second Ordre

## Forme générale quasi-linéaire à 2 variables :
$$
A \phi_{xx} +B \phi_{xy}+C \phi_{yy}=R
$$
Avec $A,B,C,R$ au plus, fonctions de $x,y,\phi_{x},\phi_{y}$

Notons bien que comme il s'agit de résoudre une équation d'ordre 2, comme pour l'intégration standard, il nous faudra 2 conditions initiales/limites pour trouver une solution unique, si elle existe.

### Types d'EDPs de Second Ordre
$$
\begin{align}
B^{2}-4AC >0 &\Rightarrow \text{Hyperbolique} \\
B^{2}-4AC =0 &\Rightarrow \text{Parabolique}   \\
B^{2}-4AC <0 &\Rightarrow \text{Elliptique} 
\end{align}
$$

## Problème de Cauchy bien posé

Le problème de Cauchy définit par l'EDP, une courbe paramétrisée $\Gamma \equiv(x(s),y(s))$ et $\phi(s)$ et $(\phi(s))_{n}$ avec $n(s)$ la direction normale à la courbe n'est que bien posé si le déterminant du système suivant :
$$
\begin{align*} \begin{pmatrix} A & B & C \\ \dfrac{dx}{ds} & \dfrac{dy}{ds} & 0 \\ 0 & \dfrac{dx}{ds} & \dfrac{dy}{ds} \\ \end{pmatrix} \begin{pmatrix} \dfrac{\partial^{2} \phi}{\partial x^{2}} \\ \dfrac{\partial \phi^{2}}{\partial x\partial y}  \\ \dfrac{\partial^{2} \phi}{\partial y^{2}} \end{pmatrix} &= \begin{pmatrix} R \\ \dfrac{d}{ds} \left( \dfrac{\partial\phi}{\partial x} \right) \\ \dfrac{d}{ds}\left( \dfrac{\partial\phi}{\partial y} \right) \end{pmatrix} \end{align*}
$$
ne s'annule en aucun point de la courbe $\Gamma$.

2. On obtient, pour un système bien posé et après maintes manipulations :
$$
\begin{align*} \begin{pmatrix} A & B & C \\ dx & dy & 0 \\ 0 & dx & dy \\ \end{pmatrix} \begin{pmatrix} \dfrac{\partial^{2} \phi}{\partial x^{2}} \\ \dfrac{\partial \phi^{2}}{\partial x\partial y}  \\ \dfrac{\partial^{2} \phi}{\partial y^{2}} \end{pmatrix} &= \begin{pmatrix} R \\ d\left( \dfrac{\partial\phi}{\partial x} \right) \\ d\left( \dfrac{\partial\phi}{\partial y} \right) \end{pmatrix} \end{align*}
$$
En définissant $u=\phi_{x}$ et $v=\phi_{y}$
### !!! Si $u$ et $v$ sont définit autrement, il faudra bien évidemment modifier le système suivant!!!

$$
\begin{align*} \begin{pmatrix} A & B & C \\ dx & dy & 0 \\ 0 & dx & dy \\ \end{pmatrix} \begin{pmatrix} u_{x} \\ u_{y}=v_{x}  \\ v_{y} \end{pmatrix} &= \begin{pmatrix} R \\ du \\ dv \end{pmatrix} \end{align*}
$$
Les deux directions caractéristiques $(dx,dy)$ sont telles que :
$$
\begin{equation} \begin{vmatrix} A & B & C \\ dx & dy & 0 \\ 0 & dx & dy \\ \end{vmatrix} \end{equation}=0 \Leftrightarrow A(dy)^{2}-Bdxdy+C(dx)^{2}=0
$$

On obtiendra donc 2 directions caractéristiques si l'EDP est hyperbolique

Bien que le déterminant du système s’annule le long des caractéristiques,
le système est encore soluble le long de ces caractéristiques à condition que le déterminant formé en remplaçant une des colonnes de la matrice par le membre de droite s’annule également, on peut aussi montrer que remplacer une colonne ou une autre donne une équation équivalente, ceci découle simplement de la définition des caractéristiques. Attention ! : Il y a une équation pour chaque caractéristique et donc on peut remplacer $dx/dy$ par $2$ expressions.

$$
\begin{vmatrix} R & B & C \\ d\phi_{x} & dy & 0 \\ d\phi_{y} & dx & dy \\ \end{vmatrix} = \begin{vmatrix} A & R & C \\ dx & d\phi_{x} & 0 \\ 0 & d\phi_{y} & dy \\ \end{vmatrix}=\begin{vmatrix} A & B & R \\ dx & dy & d\phi_{x} \\ 0 & dx & d\phi_{y} \\ \end{vmatrix}=0
$$

## Mise Sous Forme Canonique

Toute EDP d'ordre $2$ peut être réécrite sous forme canonique moyennant un changement de variable. Pour simplifier on ne regardera que le cas d'EDPs linéaires à coefficients constants. On a donc :
$$
A\phi_{xx}+B\phi_{xy}+C\phi_{yy}=F-(P\phi_{x}+Q\phi_{y}+G\phi)=R
$$
On procède en "factorisant" l'équation.
### Cas Hyperbolique
TODO : Développement qui transforme en forme canonique
### A$\neq 0$ :

$b=B/A$,$c=C/A$ et $r=R/A$

**Forme Canonique :** $\phi_{XX}-\phi_{YY}=r$

**Changement de Variables :** $X=x\quad\text{et}\quad Y=\left( -\dfrac{b}{2}x+y \right)/\sqrt{ \dfrac{b^{2}}{4}-c }$
### A$= 0$ :

$c=C/B$ et $r=R/B$

**Forme Canonique :** $\phi_{XY}=r$

**Changement de Variables :** $X=x\quad\text{et}\quad Y=(-cx+y)$


**Forme Alternative :** $\phi_{\xi \xi}-\phi_{\eta \eta}=r$

**Changement de Variables :** $X=\xi-\eta \quad\text{et}\quad Y=\xi+\eta$

### Cas Elliptique

Pas de cas $A=0$

$b=B/A$,$c=C/A$ et $r=R/A$
### A$\neq 0$ :

**Forme Canonique :** $\phi_{XX}+\phi_{YY}=r$

**Changement de Variables :** $X=x\quad\text{et}\quad Y=\left( -\dfrac{b}{2}x+y \right)/\sqrt{ c-b^{2}/4 }$

### Cas Parabolique

#### A$\neq 0$ :

$b=B/A$,$c=C/A$ et $r=R/A$

**Forme Canonique :** $\phi_{XX}=r$

**Changement de Variables :** $X=x\quad\text{et}\quad Y=-\dfrac{b}{2}x+y$


## Equivalence Système Premier Ordre et Second Ordre

Il y a, en fait, équivalence entre une EDP du 2ème ordre et un système de deux EDP du 1er ordre :

$$
A \dfrac{\partial^2 \phi}{\partial x^2} + B \dfrac{\partial^2 \phi}{\partial x \partial y} + C \dfrac{\partial^2 \phi}{\partial y^2} = R
$$

s'écrit aussi, en définissant $u = \dfrac{\partial \phi}{\partial x}$ et $v = \dfrac{\partial \phi}{\partial y}$, sous la forme:

$$
\left\{
\begin{align}
&A \dfrac{\partial u}{\partial x} + \dfrac{B}{2} \left( \dfrac{\partial u}{\partial y} + \dfrac{\partial v}{\partial x} \right) + C \dfrac{\partial v}{\partial y} = R\\
&\dfrac{\partial u}{\partial y} - \dfrac{\partial v}{\partial x} = 0
\end{align}\right.
$$
où la seconde équation provient de la compatibilité entre $u$ et $v$ :

$$ 
\dfrac{\partial u}{\partial y} = \dfrac{\partial^2 \phi}{\partial y \partial x} = \dfrac{\partial^2 \phi}{\partial x \partial y} = \dfrac{\partial v}{\partial x}.
$$

Le système équivalent du 1er ordre est donc obtenu. On obtient aussi:

$$ 
\begin{pmatrix}
A & \dfrac{B}{2} & \dfrac{B}{2} & C \\
0 & 1 & -1 & 0 \\
\dfrac{dx}{ds} & 0 & 0 & \dfrac{dy}{ds} \\
0 & \dfrac{dx}{ds} & \dfrac{dy}{ds} & 0
\end{pmatrix}
\begin{pmatrix}
\dfrac{\partial u}{\partial x} \\
\dfrac{\partial u}{\partial y} \\
\dfrac{\partial v}{\partial x} \\
\dfrac{\partial v}{\partial y}
\end{pmatrix}
=
\begin{pmatrix}
R \\
0 \\
\dfrac{du}{ds} \\
\dfrac{dv}{ds}
\end{pmatrix}.
$$


L'annulation du déterminant, afin de déterminer les directions caractéristiques, conduit à
$$
A (dy)^2 - B dy dx + C (dx)^2 = 0,
$$
(Voir : équation d'onde)

## EDP à Caractère Mixte
Certains problèmes physiques sont de type mixte. Par exemple, l'EDP de transport avec diffusion,
$$
c\,u_{x}+u_{t}=\alpha\,u_{xx}
$$
qui, mathématiquement est parabolique, il n'y a pas de méthode des caractéristiques. Cependant, et du point de vue de la physique qu’elle représente : sa composante de diffusion lui confère un caractère parabolique et sa composante de transport lui confère un caractère hyperbolique.

Il y a aussi l'équation de Burgers avec diffusion :
$$
u\cdot u_{x}+u_{t}=\alpha\,u_{xx}
$$
Dont la diffusivité $\alpha>0$ garantit la continuité de la fonction $u$.
En domaine non borné ou périodique, les deux EDP ci-dessus conservent l'intégrale de $u$ et l'énergie diminue
