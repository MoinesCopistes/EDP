# Séparation des Variables

La méthode de séparation des variables repose sur certaines propriétés fondamentales des opérateurs différentiels utilisés dans les EDPs.
#### Linéarité
Un opérateur $L$ qui agit sur les fonctions $u$ et $v$ est linéaire si, $\forall a,b\in\mathbb{R}$ :
$$
L(au+bv)=aL(u)+bL(v)
$$
Si l'EDP en question est également homogène, on peut combiner linéairement les solutions : 
$$
L(au+bv)=aL(u)+bL(v)=0
$$
C'est le ***principe de superposition***.

Le principe de la séparation des variables est de chercher la solution du problème (EDP + conditions limites) sous une forme particulière qui est souvent celle d'un produit de fonctions d'une unique variable. On cherche donc une solution de la forme suivante :
$$
u(x,y)=X(x)Y(x)
$$
L'argument donné pour ce choix de forme est que si c'est une solution au problème et que nous prouvons que la solution est unique, c'est que c'est la bonne. Cette forme ne conviendra pas à tous les systèmes EDP + conditions limites. Voir Laplace dans un rectangle pour l'exemple de séparation de variables le plus simple.

L'objectif va être, ensuite, de séparer les variables en termes indépendant pour pourvoir réduire le problème à plusieurs EDOs qu'on va pouvoir résoudre séparément puis mettre ensemble pour obtenir la solution finale. Les EDOs vont souvent prendre la forme d'un problème de Sturm-Liouville (voir page sur les problèmes de ce type).
## Exemple Illustratif : Laplace Dans un Rectangle
On cherche $u(\vec{x}),\vec{x}\in\Omega\subset \mathbb{R}^{d}$ vérifiant l'EDP :
$$
\nabla^{2}u=0
$$
#### Dans un rectangle
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

## Étapes
### 1. Séparation Des Variables
On écrit la solution sous la forme d'un produit de fonctions d'une seule variable

### 2. Substitution Dans l'EDP
On substitue le produit dans l'EDP de départ et on développe.