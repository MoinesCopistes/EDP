Un problème de Sturm-Louville est un problème de la forme :
$$
\large \frac{d}{dx}\left( p(x)\,y_{x} \right)+q(x)y=-\lambda w(x)y \Leftrightarrow \boxed{ p(x)\,y_{xx} +p(x)_{x}\,y_{x}+q(x)\,y+\lambda\,w(x)\,y=0}
$$
Où $\large p(x), q(x)$ sont des fonction données, $\large w(x)$ est la ***fonction de poids*** et $\large y$ est la ***fonction propre*** et $\large \lambda$ est la ***valeur propre***, il peut y en avoir plusieurs.

Un problème de Sturm-Liouville est dit ***régulier*** sur $\large [a,b]$ si :
1. $\large p,q,w$ et $\large p''$ sont continus sur $\large [a,b]$
2. $\large p(x),w(x)>0 \text{ sur } [a,b]$
3. Le problème a des condition limites séparables de la forme :$$\large \begin{align}\alpha_{1}y(a)+\alpha_{2}y'(a)=0\\\beta_{1}y(b)+\beta_{2}y'(a)=0\end{align}$$
   Avec au moins un des alpha et un des betas non nuls.


Les propriétés principales d'un problème de Sturm-Liouville ***régulier*** sur interval $\large [a,b]$  sont :
1. L'ensemble des valeurs propres est ***infini dénombrable***
2. À chaque valeur propre $\large \lambda_{n}$ est associée une fonction propre unique $\large y_{n}$ qui a $\large n-1$ zéros sur $\large [a,b]$ appelée la $\large n^{e}$ solution fondamentale.
3. Les fonctions propres sous forme normalisée forment une base orthonormale sous le produit scalaire de poids $\large w(x)$ de l'espace de Hilbert $\large L^{2}$ sur $\large [a,b]$ (grossièrement c'est l'ensemble qui contient la grande majorité des fonctions qu'on connait muni d'un produit scalaire), ce qu'on peut noter :
   $$\large \langle y_{n},y_{m} \rangle=\int _{a}^{b}y_{n}(x)y_{m}(x)w(x) \, dx =\delta _{nm} $$
   où est la fonction delta de Kronecker qui donne $\large 1$ si $\large n=m$ et $\large 0$ autrement.

## Le cas $\large y''+k^{2} y=0$

$\large y''+k^{2} y=0$ est un problème de Sturm-Liouville où $\large p(x)=1, q(x)=0, w(x)=1$,$\large \lambda=k^{2}$ il revient souvent dans la résolution d'EDPs par séparation de variables. On trouvera souvent que, le problème pour $\large \lambda <0$ ne donne pas de solution non triviale ou qui ont du sens physique, c'est pour cela qu'on s'intéressera surtout au cas $\large \lambda>0$ dont les résultats sont synthétisés dans le tableau suivant pour quelques conditions limites intéressantes.

| Conditions Limites | $$\large\begin{align}X(0)=0\\ X(L)=0\\\text{(Dirchlet)}\end{align}$$ | $$\large\begin{align}X'(0)=0\\ X'(L)=0\\\text{(Neumann)}\end{align}$$ | $$\large\begin{align}X(-L)=X(L)\\ X'(-L)=X'(L)\\\text{(Périodique)}\end{align}$$ |
| -------- | -------- | -------- |  -------- |
| Valeurs propres $\large k_{n}$ | $$\large \{\frac{n\pi}{L},n\in N\setminus\{0\}\}$$ | $$\large \{\frac{n\pi}{L},n\in N\}$$ | $$\large \{\frac{n\pi}{L},n\in N\}$$ |
| Fonctions propres $\large X_{n}$ | $$\large \sin(k_{n}x)$$ | $$\large \cos(k_{n}x)$$ | $$\large \sin(k_{n}x)$$ et $$\large \cos(k_{n}x)$$ |
| Séries | $$\large \sum_{n=1}^{\infty} A_{n}\sin(k_{n}x)$$ | $$\large \sum_{n=0}^{\infty} A_{n}\cos(k_{n}x)$$ | $$\large \sum_{n=1}^{\infty} A_{n}\sin(k_{n}x)$$ + $$\large \sum_{n=0}^{\infty} B_{n}\cos(k_{n}x)$$ |
| Coefficients | $$\large A_{n }=\frac{2}{L}\int_{0}^{L}f(x)\sin(k_{n}x)  \, dx$$ | $$\large \begin{align}B_{0}&=\frac{1}{L}\int_{0}^{L}f(x)\,dx \\ B_{n}&=\frac{2}{L}\int_{0}^{L}f(x)\cos(k_{n}x)  \, dx  \end{align} $$ |  $$\large \begin{align} A_{n}&=\frac{1}{L}\int_{-L}^{L}f(x)\sin(k_{n}x)  \, dx \\ B_{0}&=\frac{1}{2L}\int_{-L}^{L}f(x)\,dx \\ B_{n}&=\frac{1}{L}\int_{-L}^{L}f(x)\cos(k_{n}x)  \, dx  \end{align} $$  |

La restriction des valeurs propres pour $\large \sin(k_{n}x)$ aux naturels non-nuls provient du fait qu'on ne considère pas la solution triviale comme une fonction propre, elle ne représente pas un mode du système.
## Le cas $\large y''-k^{2} y=0$

$\large y''-k^{2} y=0$ est un problème de Sturm-Liouville où $\large p(x)=1, q(x)=0, w(x)=-1$.

$\large X(0)=0, X(L)=0$ $\large \Rightarrow$ Solution Triviale
$\large \large X'(0)=0, X'(L)=0$ $\large \Rightarrow$ Solution Triviale
$\large X(-L)=X(L),X'(-L)=X'(L)$ $\large \Rightarrow$ Solution Triviale

### Équation de Bessel

L'équation de Bessel : $\large x^{2}y_{xx} +xy_{x}+(x^{2}-\alpha^{2})y=0$ peut être écrite sous le forme de Sturm-Liouville.
$$
\large \large x^{2}y_{xx} +xy_{x}+(x^{2}-\alpha^{2})y=0\Leftrightarrow \large xy_{xx} +y_{x}+\left( x-\frac{\alpha^{2}}{x} \right)y=0
$$
$$
\large \Leftrightarrow \frac{d}{dx}(xy_{x})+\left( 1-\frac{\alpha^{2}}{x^{2}} \right)xy=0
$$
