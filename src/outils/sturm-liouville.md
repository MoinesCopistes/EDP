# Sturm-Liouville
Un problème de Sturm-Louville est un problème de la forme :
$$
\frac{d}{dx}\left( p(x)\,y_{x} \right)+q(x)y=-\lambda w(x)y \Leftrightarrow \boxed{ p(x)\,y_{xx} +p(x)_{x}\,y_{x}+q(x)\,y+\lambda\,w(x)\,y=0}
$$
Où $p(x), q(x)$ sont des fonction données, $w(x)$ est la ***fonction de poids*** et $y$ est la ***fonction propre*** et $\lambda$ est la ***valeur propre***, il peut y en avoir plusieurs.

Un problème de Sturm-Liouville est dit ***régulier*** sur $[a,b]$ si :
1. $p,q,w$ et $p''$ sont continus sur $[a,b]$
2. $p(x),w(x)>0 \text{ sur } [a,b]$
3. Le problème a des condition limites séparables de la forme :$$\begin{align}\alpha_{1}y(a)+\alpha_{2}y'(a)=0\\\beta_{1}y(b)+\beta_{2}y'(a)=0\end{align}$$
   Avec au moins un des alpha et un des betas non nuls.


Les propriétés principales d'un problème de Sturm-Liouville ***régulier*** sur interval $[a,b]$  sont :
1. L'ensemble des valeurs propres est ***infini dénombrable***
2. À chaque valeur propre $\lambda_{n}$ est associée une fonction propre unique $y_{n}$ qui a $n-1$ zéros sur $[a,b]$ appelée la $n^{e}$ solution fondamentale.
3. Les fonctions propres sous forme normalisée forment une base orthonormale sous le produit scalaire de poids $w(x)$ de l'espace de Hilbert $L^{2}$ sur $[a,b]$ (grossièrement c'est l'ensemble qui contient la grande majorité des fonctions qu'on connait muni d'un produit scalaire), ce qu'on peut noter :
   $$\langle y_{n},y_{m} \rangle=\int _{a}^{b}y_{n}(x)y_{m}(x)w(x) \, dx =\delta _{nm} $$
   où est la fonction delta de Kronecker qui donne $1$ si $n=m$ et $0$ autrement.

## Le cas $y''+k^{2} y=0$

$y''+k^{2} y=0$ est un problème de Sturm-Liouville où $p(x)=1, q(x)=0, w(x)=1$,$\lambda=k^{2}$ il revient souvent dans la résolution d'EDPs par séparation de variables. On trouvera souvent que, le problème pour $\lambda <0$ ne donne pas de solution non triviale ou qui ont du sens physique, c'est pour cela qu'on s'intéressera surtout au cas $\lambda>0$ dont les résultats sont synthétisés dans le tableau suivant pour quelques conditions limites intéressantes.

| Conditions Limites | $$\begin{align}X(0)=0\\ X(L)=0\\\text{(Dirchlet)}\end{align}$$ | $$\begin{align}X'(0)=0\\ X'(L)=0\\\text{(Neumann)}\end{align}$$ | $$\begin{align}X(-L)=X(L)\\ X'(-L)=X'(L)\\\text{(Périodique)}\end{align}$$ |
| -------- | -------- | -------- |  -------- |
| Valeurs propres $k_{n}$ | $$\{\frac{n\pi}{L},n\in N\setminus\{0\}\}$$ | $$\{\frac{n\pi}{L},n\in N\}$$ | $$\{\frac{n\pi}{L},n\in N\}$$ |
| Fonctions propres $X_{n}$ | $$\sin(k_{n}x)$$ | $$\cos(k_{n}x)$$ | $$\sin(k_{n}x)$$ et $$\cos(k_{n}x)$$ |
| Séries | $$\sum_{n=1}^{\infty} A_{n}\sin(k_{n}x)$$ | $$\sum_{n=0}^{\infty} A_{n}\cos(k_{n}x)$$ | $$\sum_{n=1}^{\infty} A_{n}\sin(k_{n}x)$$ + $$\sum_{n=0}^{\infty} B_{n}\cos(k_{n}x)$$ |
| Coefficients | $$A_{n }=\frac{2}{L}\int_{0}^{L}f(x)\sin(k_{n}x)  \, dx$$ | $$\begin{align}B_{0}&=\frac{1}{L}\int_{0}^{L}f(x)\,dx \\ B_{n}&=\frac{2}{L}\int_{0}^{L}f(x)\cos(k_{n}x)  \, dx  \end{align} $$ |  $$\begin{align} A_{n}&=\frac{1}{L}\int_{-L}^{L}f(x)\sin(k_{n}x)  \, dx \\ B_{0}&=\frac{1}{2L}\int_{-L}^{L}f(x)\,dx \\ B_{n}&=\frac{1}{L}\int_{-L}^{L}f(x)\cos(k_{n}x)  \, dx  \end{align} $$  |

La restriction des valeurs propres pour $\sin(k_{n}x)$ aux naturels non-nuls provient du fait qu'on ne considère pas la solution triviale comme une fonction propre, elle ne représente pas un mode du système.
## Le cas $y''-k^{2} y=0$

$y''-k^{2} y=0$ est un problème de Sturm-Liouville où $p(x)=1, q(x)=0, w(x)=-1$.
En général on aura $y(x)=ae^{kx}+be^{-kx}=A\cosh(kx)+B\sinh(kx)$
$X(0)=0, X(L)=0$ $\Rightarrow$ Solution Triviale
$X'(0)=0, X'(L)=0$ $\Rightarrow$ Solution Triviale
$X(-L)=X(L),X'(-L)=X'(L)$ $\Rightarrow$ Solution Triviale
## Le cas $y''=0$

$y''-k^{2} y=0$ est un problème de Sturm-Liouville où $p(x)=1, q(x)=0, w(x)=-1$.
En général on aura $y(x)=Ax+B$




### Équation de Bessel

L'équation de Bessel : $x^{2}y_{xx} +xy_{x}+(x^{2}-\alpha^{2})y=0$ peut être écrite sous le forme de Sturm-Liouville.
$$
x^{2}y_{xx} +xy_{x}+(x^{2}-\alpha^{2})y=0\Leftrightarrow xy_{xx} +y_{x}+\left( x-\frac{\alpha^{2}}{x} \right)y=0
$$
$$
\Leftrightarrow \frac{d}{dx}(xy_{x})+\left( 1-\frac{\alpha^{2}}{x^{2}} \right)xy=0
$$

## Opérateurs Auto-Adjoint
Considérons le problème avec un opérateur différentiel linéaire $L$ sur une fonction $X$   :
$$
L(X)+k^{2}X=0
$$
Soumise à des condition limites homogènes et linéaires en $x=0$ et $x=L$ :
$$
l(X)|_{0}=0\quad\text{et}\quad r(X)|_{L}=0
$$
On a donc :
$$
L(X_{n})+k^{2}_{n}X_{n}=0\quad \forall n
$$
Soient deux fonctions propres $X_{n}$ et $X_{m}$ à valeur propre distinctes, on peut écrire :
$$
X_{m}(L(X_{n})+k^{2}_{n}X_{n})=0\quad\text{et}\quad X_{n}(L(X_{m})+k^{2}_{m}X_{m})=0
$$
Dont on prend la difference et après manipulation :
$$
\begin{align}
X_{m}L(X_{n})-X_{n}L(X_{m})&=(k^{2}_{m}-k^{2}_{n})X_{n}X_{m} \\
\int_{0}^{L} X_{m}L(X_{n})-X_{n}L(X_{m}) \, dx &=(k^{2}_{m}-k^{2}_{n}) \int _{0}^{L}X_{n}X_{m} \, dx \\
\langle X_{m},L(X_{n})\rangle-\langle X_{n},L(X_{m})\rangle&=(k^{2}_{m}-k^{2}_{n})\langle X_{m},X_{n}\rangle
\end{align}
$$
Où on a définit le produit scalaire dans l'espace de fonction :
$$
\langle X_{m},X_{b}\rangle=\int _{0}^{L}X_{n}X_{m} \, dx
$$
$\langle X_{m},X_{n}\rangle$ sont orthogonaux quand le terme de gauche de l'avant dernière égalité s'annule :
$$
\langle X_{m},L(X_{n})\rangle=\langle X_{n},L(X_{m})\rangle \quad (m\neq n)
$$
Cette égalité dépend non seulement de la nature de l’opérateur, mais aussi des conditions limites associées. Quand l'équation est vérifiée, on dit que l’opérateur $L$ muni des conditions aux limites données est auto-adjoint.

**!!! Il se trouve que l'opérateur dans un problème de Sturm-Liouville régulier est auto-adjoint. !!!** 

La preuve pour $L=\frac{d}{dx^{2}}$ muni de conditions limites homogènes linéaires se fait par intégration par parties.

L'analogie entre les opérateurs auto-adjoints avec les matrices symétrique est **très forte**.