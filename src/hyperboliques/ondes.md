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

## Étude Par Séparation de Variables
La forme à plusieurs variables s'écrit :
$$
u_{tt}=c^{2}\nabla^{2}u
$$
On a $t>0$ et on considère de façon générale $\vec{x}\in\Omega\subset R^{d}$.

L'équation d'onde est un modèle pour la vibration des cordes $(d=1)$, les membranes $(d=2)$ et les solides $(d=3)$.
### Membrane Rectangulaire
Nous étudierons ici le cas $d=2$ :
$$
u_{tt}=c^{2}(u_{xx}+u_{yy})
$$
Cette équation décrit le déplacement vertical d'une membrane soumise aux conditions initiales suivantes :
$$
u(x,y,0)=u_0 (x,y)\quad x,y\in\Omega\subset R^{2}
$$
$$
\dot{u}(x,y,0)=\dot{u}_0 (x,y)\quad
$$
Qui décrivent la position et la vitesse initiale de la membrane rectangulaire de dimensions $L\times H$.

On fixe aussi la membrane à son bord $\Gamma$ par la condition limite :
$$
u(x,y,t)=0\quad \forall x,y\in \Gamma
$$
Commençons par séparer les variables qu'on va tout de suite injecter dans l'EDP :
$$
u(x,y,t)=T(t)\phi(x,y) \Rightarrow  \frac{T''}{c^{2}T}=\frac{\nabla^{2}\phi}{\phi}=\pm k^{2}
$$
On verra aussi que $+k^{2}$ donne des solutions nulles donc on fixe déjà $-k^{2}$. L'EDO en $T$ nous donne :
$$
T(t)=A\cos(kct)+B\sin (kct)
$$
En $\phi$ on a :
$$
\nabla^{2}\phi+k^{2}\phi=0
$$
Celui-ci avec la condition limite homogène est un **problème de Helmholtz**. On peut prouver que $\nabla^{2}$ est un opérateur auto-adjoint et que donc les fonctions propres sont orthogonales et qu'il en existe un nombre infini.

Pour résoudre ce problème de Helmholtz, on va encore séparer les variables qu'on va injecter dans le problème de Helmholtz :
$$
\phi(x,y)=X(x)Y(y) \Rightarrow \frac{X''}{X}=-k^{2}-\frac{Y''}{Y}=-l^{2}
$$
Avec $l$ encore une constante. Encore une fois, le signe négatif est choisi pour éviter les solutions non-triviales, on trouve alors avec les bords fixes donc des conditions de Dirichlet homogène que :
$$
l=\frac{n\pi}{L}\,\,|\,\,n\in N_{0}\quad \text{et}\quad X(x)=D\sin(lx)
$$
En $Y$ on a :
$$
Y(y)=E\cos(\sqrt{ k^{2}-l^{2} }y)+F\sin(\sqrt{ k^{2}-l^{2} }y)
$$
Et avec les conditions initiales :
$$
\sqrt{ k^{2}-l^{2} }=\frac{m\pi}{H}\,\,|\,\,m\in N_{0}\quad\text{et}\quad Y(y)=\sin\left( \frac{m\pi}{H}y \right)
$$
Qu'on peut combiner avec l'expression de $l$ pour trouver :
$$
k^{2}=\left( \frac{m\pi}{H} \right)^{2}+\left( \frac{n\pi}{L} \right)^{2}
$$
Les fonctions propres du Laplacien dans un rectangle sont :
$$
\phi_{nm}(x,y)=X_{n}(x)Y_{m}(y)=\sin\left( \frac{n\pi}{L}x \right)\sin\left( \frac{m\pi}{H}y \right)
$$
Dont l'orthogonalité s'écrit :
$$
\int _{0}^{L}\int _{0}^{H}\phi_{mn}(x,y)\phi_{ij}(x,y) \, dx  \, dy=\frac{HL}{4}\delta _{im}\delta _{jn}
$$
Les **fréquences propres** $\omega_{mn}$ de la membrane sont :
$$
\boxed{\omega_{mn}=c\sqrt{ \left( \frac{m\pi}{H} \right)^{2}+\left( \frac{n\pi}{L} \right)^{2} }}
$$
On a donc la solution provisoire de l'EDP + condition limite :
$$

\begin{align}
u(x,y,t)=\sum_{m=1}^{\infty}\sum_{n=1}^{\infty}[&A_{mn}\cos(\omega_{mn} ct)  +B_{mn}\sin(\omega_{mn}ct)] \\
\cdot &\sin(\frac{n\pi}{L}x)\sin(\frac{m\pi}{H}y)
\end{align}
$$
On applique donc la condition initiale sur la position :
$$
u(x,y,0)=u_0 (x,y)=\sum_{m=1}^{\infty}\sum_{n=1}^{\infty}A_{mn}\sin\left( \frac{n\pi}{L}x \right)\sin\left( \frac{m\pi}{H}y \right)
$$
Et en appliquant l'orthogonalité on peut trouver :
$$
A_{mn}=\frac{4}{LH} \int _{0}^{L}\int _{0}^{H}u_{0}(x,y)\sin\left( \frac{n\pi}{L}x \right)\sin\left( \frac{m\pi}{H}y \right) \, dx  \, dy 
$$
Et $B_{n}$ se trouve en appliquant l'orthogonalité à :
$$
\dot{u}_{0}(x,y)=\sum_{m=1}^{\infty}\sum_{n=1}^{\infty}B_{mn}\omega_{mn}\sin\left( \frac{n\pi}{L}x \right)\sin\left( \frac{m\pi}{H}y \right)
$$
Dans le cas d'une vitesse initiale nulle on aura $B_{mn}=0$ mais sinon :
$$
B_{mn}=\frac{4}{LH} \frac{1}{\omega_{mn}} \int _{0}^{L}\int _{0}^{H}\dot{u}_{0}(x,y)\sin\left( \frac{n\pi}{L}x \right)\sin\left( \frac{m\pi}{H}y \right) \, dx  \, dy 
$$
Ces coefficients sont absolument infernaux à calculer donc en pratique on le fait numériquement.
### Membrane Circulaire
Pour résoudre le problème dans un domaine circulaire de rayon $a$, on va utiliser l'équation d'onde sous forme polaire :
$$
u_{tt}=c^{2}\nabla^{2}u=c^{2}\left( \frac{1}{r} \frac{\partial}{\partial r}\left( r u_{r} \right) + \frac{1}{r^{2}} u_{rr} \right)
$$
Cette équation décrit le déplacement vertical d'une membrane soumise aux conditions initiales suivantes :
$$
u(r,\theta,0)=u_0 (r,\theta)
$$
$$
\dot{u}(r,\theta,0)=\dot{u}_0 (r,\theta)
$$
On fixe aussi la membrane à son bord $\Gamma$ par la condition limite :
$$
u(a,\theta,t)=0
$$
On sépare l'espace et le temps et on le met dans l'équation de départ :
$$
u(r,\theta,t)=T(t)\phi(r,\theta) \Rightarrow T''(t)\phi(r,\theta)=c^{2}T(t)\nabla^{2}\phi(r,\theta) 
$$
$$
\Rightarrow \frac{T''}{c^{2}T}=\frac{\nabla^{2}\phi}{\phi}=-k^{2} 
$$
Pour $T$ on trouve de nouveau :
$$
T(t)=A\cos(kct)+B\sin(kct)
$$
Pour $\phi$ on sépare les variables :
$$
\phi(x,y)=R(r)\Theta(\theta)
$$
Qu'on injecte dans le problème de Helmholtz avec la Laplacien exprimé en coordonnées polaires :
$$
\nabla^{2}\phi+k^{2}=\Theta   \frac{1}{r}(rR')'+\frac{1}{r^{2}}R\Theta''+k^{2}R\Theta=0
$$
Après division et avec une nouvelle constante $m$ on trouve :
$$
\frac{1}{R} r(rR')'+k^{2}r^{2}=-\frac{1}{\Theta}\Theta''=m^{2}
$$
En $\theta$ on trouve :
$$
\Theta(\theta)=A\cos(m\theta)+B\sin(m\theta)\,\,|\,\,m\in N
$$
En $r$ :
$$
r^{2}R''+rR'+(k^{2}r^{2}-m^{2})R=0
$$
Qui n'est pas une équation d'Euler (donc on ne peut pas trouver les solution en substituant $R=r^{\alpha}$) mais si on pose :
$$
\boxed{z=kr}
$$
On obtient une équation différentielle de Bessel d'ordre $m$ :
$$
\boxed{z^{2}R''+zR'+(z^{2}-m^{2})R=0}
$$
Dont la solution s'exprime par une combinaison des deux espèces de **fonctions de Bessel** (voir page sur les fonctions de Bessel) :
$$
R(z)=AJ_{m}(z)+BY_{m}(z)
$$
Comme on a aussi :
$$
R(a)=0
$$
Et que les fonctions de Bessel de seconde espèce présentent une singularité en $0$, on en déduit que $B=0$ (si $0$ ne faisait pas partie du domaine on aurait pas pu rejeter les $Y$), la condition limite donne alors :
$$
J_{m}(ka)=0
$$
Les $k_{mn}$ sont donc donnés par les zéros de la $m^{e}$ fonction de Bessel :
$$
 \boxed{k_{mn}=\frac{z_{mn}}{a}}
$$
Les fonctions/modes propres du problème de Helmholtz circulaire avec la condition de Dirichlet Homogène sont donc :
$$
\phi_{mn}(r,\theta)=J_{mn}\left( \frac{z_{mn}}{a}r \right)(A\cos(m\theta)+B\sin(m\theta))
$$
Dont l'orthogonalité s'écrit :
$$
\int_{\Omega}\phi_{mn}(r,\theta)\phi_{ij}(r,\theta)  \, ds=0 
$$
Si on remplace les expressions de chaque terme dans l'expression de l'orthogonalité, on trouve :
$$
\int _{0}^{2\pi}\sin(m\theta)\sin(i\theta)\, d\theta\int _{0}^{a}J_{m}\left( \frac{z_{mn}}{a}r \right)J_{i}\left( \frac{z_{ij}}{a}r \right)r \, dr   =0
$$
Les deux termes de cette égalité sont tous deux simultanément nuls. On a donc :
$$
\int _{0}^{a}J_{m}\left( \frac{z_{mn}}{a}r \right)J_{i}\left( \frac{z_{ij}}{a}r \right)r \, dr   =0
$$
Pour simplifier les notations, choisissons une vitesse initiale nulle. Dans ce cas, $T_{mn}(t) = A \cos(ck_{mn}t)$ et la solution du problème avec C.L. nulles est :
$$

\begin{align}
u(r,\theta,t)=&\sum_{m=0}^{\infty}\sum_{n=1}^{\infty}A_{mn}J_{m}\left( \frac{z_{mn}}{a}r \right)\cos(m\theta)\cos\left( \frac{z_{mn}}{a}ct \right) + \\
&\sum_{m=1}^{\infty}\sum_{n=1}^{\infty}B_{mn}J_{m}\left( \frac{z_{mn}}{a}r \right)\sin(m\theta)\cos\left( \frac{z_{mn}}{a}ct \right)
\end{align}
$$
On utilise l'orthogonalité pour calculer les coefficients :
$$
\int _{0}^{2\pi}\int _{0}^{a}u_{0}(r,\theta)J_{m}\left( \frac{z_{mn}}{a}r \right)\cos(m\theta)r \, dr  \, d\theta =A_{mn}\pi \int _{0}^{a}J^{2}_{m}\left( \frac{z_{mn}}{a}r \right) \,r dr 
$$
Considérons le cas (simple) où $u_{0}$ est indépendant de $θ$. Dans ce cas, seul les termes relatifs à $m = 0$ sont non nuls et la solution est indépendante de $θ$. Le cas d’une vitesse initiale nulle et $u_{0}(r)$ indépendant de $θ$ donne donc :
$$
u(r,t)=\sum_{n=1}^{\infty}A_{n}J_{0}\left( \frac{z_{0n}}{a}r \right)\cos\left( \frac{z_{0n}}{a}ct \right)
$$
Et :
$$
A_{n}=\frac{\left( \int_{0}^{a}u_{0} (r)J_{0}\left( \frac{z_{0n}}{a}r \right) \, rdr  \right)}{\int _{0}^{a}J^{2}_{0}\left( \frac{z_{0n}}{a}r \right) \, dr }
$$



