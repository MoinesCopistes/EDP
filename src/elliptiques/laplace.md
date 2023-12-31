# Équation de Laplace
## Forme Générale 2D
$$
\phi_{xx}+\phi_{yy}=0\Leftrightarrow \nabla^{2}\phi=0
$$
Avec $A=1,B=0,C=1,R=0\Rightarrow$ ***Elliptique***. Les solution des équations des caractéristiques sont imaginaires, il n'y en a pas.

Les problèmes elliptiques doivent être résolus de manière globale: tous les points influencent tous les points! Ces problèmes sont toujours résolus sur un domaine physique $\Omega$. Si le domaine est borné, il faut donner une condition en tout point de sa frontière $\partial \Omega$ paramétrisée par $s$. On y prescrit soit la fonction $\phi(s)$ (Dirichlet), soit la dérivée normale$\frac{\partial \phi}{\partial n}(s)$ (Neumann), soit une condition mixte (Robin).
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
## Propriétés

### Théorème de La Valeur Moyenne
(Voir Laplace dans un cercle par séparation des variables.)
Soit la solution $u$ de l'équation de Laplace dans un domaine $\Omega$ ouvert de plan $xy$ quelconque. Considérons le cercle $B$ de rayon $a$ et de centre $\vec{c}(x,y)$ complètement inclus dans $\Omega$. La valeur $u(x,y)$ est égale à :
- La moyenne : 
  $$\frac{1}{2\pi a} \oint_{\partial B}u\,dl $$
  de $u$ calculée sur la circonférence de n'importe quel cercle centré en $(x,y)$
- La moyenne :
  $$\frac{1}{\pi a^{2}} \int_{B}u\,ds $$
  de $u$ calculée sur la surface du cercle.
Note : La proposition inverse est également vraie. Si la valeur de $u(x,y)$ en un point est égale à la moyenne de $u$ sur n'importe quel cercle centré en ($x,y$) inclus dans $\Omega$, alors $u$ est solution de l'équation de Laplace.
### Théorème du Maximum
Soit la solution $u$ de l'équation de Laplace dans un domaine $\Omega$ ouvert de plan $xy$ quelconque. Nous allons démontrer qu'il n'est pas possible que $u(x,y)$ soit maximale en un point $\vec{c}(x,y)$ intérieur à $\Omega$.

L'idée de la preuve est que, comme la valeur de chaque point correspond à la moyenne des points sur une cercle centré en ce point, par le théorème de la moyenne, il n'est pas possible que la valeur de la fonction dépasse les valeurs des points sur les cercle.

Par l'absurde : Considérons qu'il existe un maximum local à $u$ en $\vec{c}(x,y)$. Il existe donc un voisinage $V$ de $\vec{c}(x,y)$ tel que : $\forall\vec{p}(X,Y)\in V$, $u(X, Y) < u(x, y)$. On considère un cercle $B$ de rayon $\epsilon$ centré en $\vec{c}(x,y)$ et complètement inclus dans $V$. Soit $U$ la valeur maximale de $u$ sur le cercle. On sait, par le théorème de la valeur moyenne, que :
$$
2\pi\, a\,u(x,y)=\oint_{\partial B}u\,dl<2\pi aU
$$
Or, $u$ est maximal en $\vec{c}(x,y)$, ce qui implique que $u>U$, ce qui contredit le théorème de la moyenne. **La valeur maximale de $u$ est donc toujours atteinte sur $\partial \Omega$.**
### Théorème du Minimum
La valeur minimale de $u$ est donc toujours atteinte sur $\partial \Omega$.
### Unicité de la Solution de l'Équation de Laplace
Soit $u(x,y)$ solution de l'équation de Laplace soumises à des conditions de Dirichlet :
$$
u=\bar{u}\quad\text{sur} \quad \partial\Omega
$$
Imaginons qu'il existe une autre fonction $v(x,y)$ solution de l'équation de Laplace soumises aux mêmes conditions limites :
$$
v=\bar{u}\quad\text{sur}\quad \partial\Omega
$$
L'EDP de Laplace est une EDP linéaire, on a donc :
$$
\nabla^{2}(u-v)=\nabla^{2}u-\nabla^{2}v=0\quad \text{dans}\quad \Omega
$$
Les conditions aux limites sont elles aussi linéaires, on a donc :
$$
(u-v)=\bar{u}-\bar{u}=0\quad \text{sur}\quad \partial \Omega
$$
La fonction $u-v$ est donc solution de l'équation de Laplace soumise à des condition de Dirichlet identiquement nulles. Étant donné le théorème du maximum, $u-v\leq 0$ dans $\Omega$. Étant donné le théorème du minimum, $u-v\geq 0$ dans $\Omega$. On a donc $u-v=0$ partout dans $\Omega$.

## Étude Par Séparation de Variables

On cherche $u(\vec{x}),\vec{x}\in\Omega\subset \mathbb{R}^{d}$ vérifiant l'EDP :
$$
\nabla^{2}u=0
$$
### Dans un rectangle
#### Avec 3 Conditions Limites Homogènes et Une Non Homogène
$\Omega=\{x,y|0<x<L,0<y<H\}$, conditions limites linéaires et homogènes sur 3 des 4 frontières, une condition limite linéaire et non homogène sur la quatrième. On cherche une solution de la forme suivante qu'on injecte dans l'EDP:
$$
u(x,y)=X(x)Y(y)\Rightarrow\nabla^{2}u= X''Y+XY'' =0
$$
On peut diviser par $XY$ et obtenir :
$$
\frac{X''}{X}=-\frac{Y''}{Y}
$$
Comme on a une égalité entre 2 fonctions de variables distinctes vérifiée pour toutes les valeurs des variables, on peut en déduire que chacun des termes sont constants.
$$
\frac{X''}{X}=-\frac{Y''}{Y}=\pm k^{2}\Leftrightarrow X''=\pm k^{2}X \quad \text{et} \quad Y''=\mp k^{2}Y
$$
Ce sont les problèmes de Sturm-Liouville les plus basiques dont les solutions sont données dans la page sur Sturm-Liouville.
Comme on a $X$ homogène sur les frontières, on doit avoir $-k^{2}$ :
$$
k_{n}=\frac{n\pi}{L}|n\in N_{0}\quad\text{et}\quad  X_{n}(x)=B_{n}\sin\left( k_{n}x \right)
$$
Et pour $Y$, avec $k^{2}$ et une condition homogène en $y=0$ :
$$
Y_{n}(y)=a_{n}e^{k_{n}y}+be^{-k_{n}y}\quad \text{et}\quad Y(0)=a+b=0
$$
$$
\Rightarrow Y_{n}(y)=a_{n}(e^{k_{n}y}-e^{-k_{n}y})=A_{n}\sinh(k_{n}y) 
$$
On a donc, provisoirement, la solution :
$$
u(x,y)=\sum_{n=1}^{\infty}C_{n}\sin(k_{n}x)\sinh(k_{n}y)
$$
On doit maintenant traiter la condition non-homogène en $y=H$, qu'on peut noter : $u(x,H)=f(x)$ :
$$
u(x,H)=\sum_{n=1}^{\infty}C_{n}\sin(k_{n}x)\sinh(k_{n}H)=\sum_{n=1}^{\infty}D_{n}\sin(k_{n}x)=f(x)
$$
Les propriétés du problème de Sturm-Liouville nous permettent de savoir que les $\sin(k_{n}x)$ forment une base de l'espace de fonctions qui contient la condition non-homogène. La détermination des constantes correspond alors à une projection de la condition non-homogène dans la base, ce qui se fait par le produit scalaire définit par le problème de Sturm-Liouville :
$$\langle y_{n},y_{m} \rangle=\int _{a}^{b}y_{n}(x)y_{m}(x)w(x) \, dx =\delta _{nm} $$
Où les $y$ sont normalisés, en pratique on utilise pas toujours les formes normalisées donc on aura $a\cdot \delta_{nm}$ ($a\in\mathbb{R}$). Dans ce cas on a une fonction de poids unitaire, ce qui simplifie les choses :
$$
 
\begin{align}
\sum_{n=1}^{\infty}D_{n}\sin(k_{n}x)&=f(x) \\
\sum_{n=1}^{\infty}D_{n}\sin(k_{n}x) \sin(k_{m}x) &=f(x)\sin(k_{m}x) \\
\int_{0}^{L}    \sum_{n=1}^{\infty}D_{n}\sin(k_{n}x)\sin(k_{m}x)\, dx&=\int_{0}^{L} f(x)\sin(k_{m}x)\, dx \\
\sum_{n=1}^{\infty}D_{n}\int_{0}^{L}    \sin(k_{n}x)\sin(k_{m}x)\, dx&=\int_{0}^{L} f(x)\sin(k_{m}x)\, dx

\end{align}  
$$
Où on élimine les $k_{n}$ avec $n\neq m$ :
$$
D_{n}\int_{0}^{L}   \sin^{2}(k_{m}x)\, dx=D_{n} \frac{L}{2}=\int_{0}^{L} f(x)\sin(k_{m}x)\, dx
$$
$$
\Rightarrow C_{n}\sinh(k_{n}H)=\frac{2}{L} \int_{0}^{L} f(x)\sin(k_{m}x)\, dx 
$$
$$
\Rightarrow  C_{n}=\frac{1}{\sinh(k_{n}H)}\frac{2}{L} \int_{0}^{L} f(x)\sin(k_{m}x)\, dx
$$
Et la solution générale :
$$
\boxed{u(x,y)=\sum_{n=1}^{\infty}\frac{1}{\sinh(k_{n}H)}\frac{2}{L} \int_{0}^{L} f(x)\sin(k_{m}x)\, dx\sin(k_{n}x)\sinh(k_{n}y)}
$$
On va citer $2$ particuliers de $f(x)$ :
1. $f(x)=u_{0}$ qui donne :
   $$\boxed{u(x,y)=2u_{0}\sum_{n=1}^{\infty}\frac{(1-(-1)^{n})}{n\pi\sinh(k_{n}H)} \sin(k_{n}x)\sinh(k_{n}y)}$$
   La solution oscille aux points $(x,y)=(0,H)$ et $(L,H)$, c'est ce qui arrive quand on développe une constante en série de sinus.
2. $f(x)=u_{0} \frac{x}{L}\left( 1-\frac{x}{L} \right)$, dont le calcul de l'intégrale est bien plus long et nous donne finalement : $$\int_{0}^{L}\sin(k_{n}x) \frac{x}{L} \left( 1-\frac{x}{L} \right)  \, dx =\frac{2L(1-(-1)^{n})}{(n\pi)^{3}}$$ $$\boxed{u(x,y)=4u_{0}\sum_{n=1}^{\infty}\frac{(1-(-1)^{n})}{(n\pi)^{3}\sinh(k_{n}H)} \sin(k_{n}x)\sinh(k_{n}y)}$$ 
#### Avec Une Condition de Robin
TODO : Interprétation Physique

On va par exemple étudier la solution en régime de la température dans une surface 2D sans sources. Pour l'interprétation d'une condition limite de Robin, voir la page sur l'équation de la chaleur.

On impose donc les conditions limites suivantes :
$$

\left\{
\begin{align}
&-\kappa T_{x}(0,y)=0 \\
&-\kappa T_{y}(x,0)=0 \\
&T(L,y)=T_{0} \\
&-\kappa T_{y}(x,H)=h(T(x,H)-T_{\infty})
\end{align}
\right.
$$
On cherche don une famille de fonctions : 
$$u_{n}(x,y)=X_{n}(x)Y_{n}(y)$$
Si on essaye d'appliquer les condition limites aux solution des problèmes de Sturm-Liouville tel quel, on aura beaucoup de difficulté à trouver les $k_{n}$ et à determiner la bonne forme des solutions, nous allons voir 2 méthodes pour quand même y arriver :

##### Changement de Variable $1$ $u=(T-T_{\infty})$ :
Ce qui nous donne les conditions limites :
$$

\left\{
\begin{align}
&u_{x}(0,y)=0 \\
&u_{y}(x,0)=0 \\
&u(L,y)=T_{0}-T_{\infty} \\
&-\kappa\, u_{y}(x,H)=h\,u(x,H)
\end{align}
\right.
$$
Ce qui nous donne $3$ conditions limites homogènes !

On part alors de :
$$
\frac{X''}{X}=-\frac{Y''}{Y}=\pm k^{2}
$$
Et on trouvera pour $Y$ que $+k^{2}$ donne :
$$
Y(y)=A\cos(ky)+B\sin(ky)
$$
Qui après application de la condition $u_{y}(x,0)=0$ donne :
$$
Y(y)=A\sin(ky)
$$
Et avec $-\kappa\, u_{y}(x,H)=h\,u(x,H)$ on aura l'équation transcendante :
$$
k=\frac{h}{\kappa}\cot(kh)
$$
Dont on notera $k_{n}$ ($n\in N_{0}$) les solution.

Si on prends $-k^{2}$, on arrive à l'équation suivante pour $k$ qui n'a pas de solutions :
$$
-k=\frac{h}{k}\coth(kH)
$$
On a donc déterminé les $k_{n}$ il reste à trouver une expression pour $X$


$+k^{2}$ pour $X$ nous donne :
$$
X_{n}(x)=E_{n}\sinh(k_{n}x) + F_{n}\cosh(k_{n}x)
$$
Avec la condition limite $u_{x}(0,y)=0$ on trouve :
$$
X_{n}(x)=G_{_{n}}\cosh(k_{n}x)
$$
La solution pour l'EDP avec les conditions limites homogènes nous donne donc :
$$
u(x,y)=\sum_{n=1}^{\infty}A_{n}\cosh(k_{n}x)\cos(k_{n}y)
$$
On peut calculer les $A_{n}$ par orthogonalité appliquée sur la condition limites non-homogène :
$$
T_{0}-T_{\infty}=\sum_{n=1}^{\infty}A_{n}\cosh(k_{n}x)\cos(k_{n}y)
$$
On multiplie par $\cos(k_{m}y)$ puis on intègre sur $[0,H]$ et on trouvera, après calcul sans grosses surprises que :
$$
A_{m}=4 \frac{T_{0}-T_{\infty}}{\cosh(k_{m}L)} \frac{\sin(k_{m}H)}{2k_{m}H+\sin(2k_{m}H)}
$$
##### Changement de Variable $1$ $u=(T-T_{0})$ :
$$

\left\{
\begin{align}
&u_{x}(0,y)=0 \\
&u_{y}(x,0)=0 \\
&u(L,y)=0 \\
&-\kappa\, u_{y}(x,H)-h\,u(x,H)=h(T_{0}-T_{\infty})
\end{align}
\right.
$$
On a donc $2$ conditions homogène en $y$ ce qui nous permet de trouver facilement $X$ comme :
$$
X_{n}=A_n \cos(k_{n}x)
$$
Et :
$$
k_{n}=\left( \frac{(2n-1)\pi}{2L} \right)\quad (n\in N_{0})
$$
Pour $Y_{n}$ on trouve :
$$
Y_{n}(y)=C_{n}\cosh(k_{n}y)
$$
On trouve donc la solution pour l'EDP + les condition homogènes :
$$
u(x,y)=\sum^{\infty}_{n=1}A_{n}\cos(k_{n}x)\cosh(k_{n}y)
$$
Et on doit calculer sa dérivée pour pouvoir appliquer la condition limite non-homogène :
$$
u_{y}(x,y)=\sum^{\infty}_{n=1}A_{n}k_{n}\cos(k_{n}x)\sinh(k_{n}y)
$$
La condition limite donne alors :
$$
h(T_{0}-T_{\infty})=-\sum_{n=0}^{\infty}A_{n}\cos(k_{n})(h\cosh(k_{n}H)+\kappa k_{n}\sinh(k_{n}H))
$$
Et hop rebelotte on multiplie par $\cos(k_{m}x)$, on intègre, on supprime les termes qui s'annulent et on trouve :
$$
A_{m}=\frac{2}{L} \frac{h(T_{0}-T_{\infty}) \frac{1}{k_{m}}(-1)^{m}}{h\cosh(k_{m}H)+\kappa k_{m}\sinh(k_{m}H)}
$$
On peut finalement trouver une expression pour la température :
$$
\boxed{\frac{T_{0}-T(x,y)}{T_{0}-T_{\infty}}=\sum_{n=1}^{\infty}\frac{2}{Lk_{n}} \frac{h (-1)^{n+1}\cos(k_{n}x)\cosh(k_{n}y)}{h\cosh(k_{n}H)+\kappa k_{n}\sinh(k_{n}H)}}
$$
💀
### Dans un Cercle
On demande de calculer le profil de température stationnaire $u(r,\theta)$ dans un cercle de rayon $r=a$, les conditions aux limites sont :
$$
u(r=a,\theta)=f(\theta)
$$
On va donc résoudre ce problème en coordonnées polaires pour transformer le domaine circulaire en domaine rectangulaire, l'équation de la chaleur stationnaire ou l'équation de Laplace en coordonnées polaires est :
$$
\nabla^{2}u=0\Leftrightarrow \frac{1}{r} \frac{\partial}{\partial r}(r\,u_{r})+\frac{1}{r^{2}}\,u_{\theta \theta}=0\Leftrightarrow u_{rr}+\frac{1}{r} u_{r}+\frac{1}{r^{2}} u_{\theta \theta}=0
$$
On applique la séparation des variables :
$$
u(r,\theta)=R(r)\Theta(\theta)\Leftrightarrow R''\Theta+\frac{1}{r}R'\Theta+\frac{1}{r^{2}} R \Theta''=0
$$
$$
\Leftrightarrow \frac{R''+\frac{1}{r}R'}{R}+\frac{1}{r^{2}} \frac{\Theta''}{\Theta}=0\Leftrightarrow \frac{r^{2}R''+rR'}{R}=-\frac{\Theta''}{\Theta}=\pm  k^{2}
$$
En $\theta$ on a donc un problème de Sturm-Liouville basique sur un domaine périodique de période $2\pi$ ce qui ne donnera que des solutions non triviales pour $-k^{2}$. Le $L$ dans la formule correspond à une demi période ce qui, ici, correspond à $\pi$, on a donc :
$$
k_{n}=n\,\,|\,\,n\in \mathbb{N} \quad \text{et} \quad\Theta_{n}(\theta)=A_{n}\cos(n\theta)+B_{n}\sin(n\theta)
$$
L'équation en $r$ donne :
$$
r^{2}\,R_{rr}+r\,R_{r}-k_{n}^{2}\,R=0
$$
Qui est une équation d'Euler qui se résout en remplaçant $R$ par une solution du type $r^{\alpha}$ (on peut le comprendre intuitivement, comment annuler des termes qui ont des puissances de $r$ à des puissances différentes en produit ? $r^{\alpha}$ pourrait être une réponse).
$$
r^{2}r^{\alpha-2}(\alpha)(\alpha-1)+rr^{\alpha-1}\alpha-k^{2}_{n}r^{\alpha}=0\Leftrightarrow \alpha^{2} - \alpha +\alpha-k^{2}=0
$$
$$
\Leftrightarrow \alpha=\pm k_{n}\Rightarrow R_{n}(r)=C_{n}r^{k_{n}}+D_{n}r^{-k_{n}} 
$$
Cependant, il y aura une division par $0$ si $r=0$ donc $D_{n}$ doit être nul pour avoir une solution physique.
On a donc, avec l'EDP + les conditions sur $\theta$ :
$$
u(r,\theta)=\sum_{n=0}^{\infty}(A_{n}\cos(n\theta)+B_{n}\sin(n\theta))C_{n}r^{n} 
$$
Ce qu'on peut réécrire, en redéfinissant $A_{n}$ et $B_{n}$ :
$$
u(r,\theta)=A_{0}+\sum_{n=1}^{\infty}r^{n}(A_{n}\cos(n\theta)+B_{n}\sin(n\theta))
$$
Dont on trouve les coefficients par orthogonalité des sinus/cosinus et avec la condition limite sur $r=a$.
$$

\begin{align}
A_{0}&=\frac{1}{2\pi} \int_{0}^{2\pi}f(\theta)  \, d\theta \\
A_{n}&=\frac{1}{\pi a^{n}} \int_{0}^{2\pi}f(\theta) \cos(n\theta) \, d\theta \\
B_{n}&=\frac{1}{\pi a^{n}} \int_{0}^{2\pi}f(\theta) \sin(n\theta) \, d\theta
\end{align}
$$
La solution au centre du cercle vaut la moyenne de la température imposée en $r=a$ :





