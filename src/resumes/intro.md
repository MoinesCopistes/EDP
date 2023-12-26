# Introduction

## Terminologie

Une EDP est une équation qui fait intervenir une variable $\large u$ dépendante de $\large m$ variables *indépendantes* $\large x_{1},x_{2},\dots x_{m}$ et les dérivées partielles de $\large u$ par rapport à ces variables. Une telle équation est :
1. ***d'ordre $\large n$*** quand la dérivée partielle d’ordre le plus élevé qu’elle contient est d’ordre $\large n$.
   Ex :  $\large \frac{\partial^{2}u}{\partial x^{2}}+\frac{\partial^{2}u}{\partial y^{2}}=0$, est d'ordre $\large 2$, $\large \large \frac{\partial^{3}u}{\partial x^{3}}+\frac{\partial^{2}u}{\partial y^{2}}=0$ est d'ordre $\large 3$
3. ***homogène*** si elle ne contient que des termes faisant intervenir $\large u$ et ses dérivées partielles.
   Ex :  $\large \frac{\partial^{2}u}{\partial x^{2}}+\frac{\partial^{2}u}{\partial y^{2}}=0$, est d'ordre homogène, $\large \large \frac{\partial^{3}u}{\partial x^{3}}+\frac{\partial^{2}u}{\partial y^{2}}=1$ n'est pas homogène, $\large \large \frac{\partial^{3}u}{\partial x^{3}}+\frac{\partial^{2}u}{\partial y^{2}}=u$ non plus.
4. ***linéaire*** quand elle l’est par rapport à toutes les dérivées partielles de $\large u$ et par rapport à $\large u$. C'est à dire qu'on peut pas avoir de dérivées partielles à un $\large 2$ par exemple ou dans une fonction trigonométrique.
5. ***quasi-linéaire*** quand elle l’est par rapport aux dérivées partielles d’ordre le plus élevé en chacune des variables. Même contrainte que linéaire mais limité aux dérivées partielles ***de plus grand ordre de chacune des variables***.

## Problème Bien Posé

Un problème est dit "bien-posé" si :
1. Le problème a une solution
2. La solution est unique
3. La solution dépend continuellement des données du problème.

## Conditions Limites

Les conditions aux limites pour les équations aux dérivées partielles (EDP) sont cruciales pour déterminer une solution unique à un problème donné. Il existe trois types principaux de conditions aux limites:

1. **Condition de Dirichlet** : Cette condition spécifie la valeur de la solution le long d'une frontière du domaine. Par exemple, pour une EDP $u(x,t)$ définie dans un domaine $D$, la condition de Dirichlet peut être exprimée comme:$$u(x,t) = h(x,t), \quad \forall (x,t) \in \partial D$$
   où $\partial D$ est la frontière de $D$ et $h(x,t)$ est une fonction donnée.

2. **Condition de Neumann** : Ici, c'est la dérivée normale de la solution qui est spécifiée à la frontière. Pour une EDP $u(x,t)$, la condition de Neumann est donnée par:
   $$
   \frac{\partial u}{\partial n}(x,t) = k(x,t), \quad \forall (x,t) \in \partial D
   $$
   où $\frac{\partial u}{\partial n}$ est la dérivée de $u$ dans la direction normale à la frontière $\partial D$ et $k(x,t)$ est une fonction connue.

3. **Condition de Robin (ou condition aux limites mixtes)** : Cette condition est une combinaison linéaire des deux premières, où à la fois la fonction et sa dérivée normale sont spécifiées:
   $$
   a(x,t) u(x,t) + b(x,t) \frac{\partial u}{\partial n}(x,t) = g(x,t), \quad \forall (x,t) \in \partial D
   $$
   avec $a(x,t)$ et $b(x,t)$ des fonctions données sur la frontière, et $g(x,t)$ une autre fonction spécifiée.

**Exemples (À Vérifier) :**

- **Dirichlet** : Pour l'équation de la chaleur $u_t = \alpha^2 u_{xx}$ dans une barre métallique de longueur $L$, on peut avoir une température fixe aux deux extrémités, soit $u(0,t) = T_0$ et $u(L,t) = T_L$ pour tout temps $t$.

- **Neumann** : Pour la même équation de la chaleur, si les extrémités de la barre sont isolées thermiquement, la dérivée de la température par rapport à $x$ est nulle aux deux bouts, donc $\frac{\partial u}{\partial x}(0,t) = 0$ et $\frac{\partial u}{\partial x}(L,t) = 0$.

- **Robin** : Si une extrémité de la barre est en contact avec un milieu dont la température est $T_m$ et que la loi de refroidissement de Newton s'applique, alors on pourrait avoir une condition de la forme $-k \frac{\partial u}{\partial x}(L,t) = h(u(L,t) - T_m)$, où $k$ est la conductivité thermique et $h$ est le coefficient de transfert de chaleur.

## Domaines 

Les types de domaines déterminent la nature de la solution et la méthode de résolution. Les trois principaux types de domaines sont:

1. **Domaine borné** : Le domaine est limité dans toutes les directions. Les conditions aux limites doivent être spécifiées sur la frontière finie du domaine pour obtenir une solution unique. 
   
   *Exemple*: Pour l'équation de Laplace $\nabla^2 \phi = 0$ dans une région rectangulaire, les valeurs de $\phi$ doivent être données sur tout le périmètre pour résoudre l'EDP.

2. **Domaine non borné** : Au moins dans une direction, le domaine s'étend à l'infini. Les conditions aux limites à l'infini doivent souvent supposer que la solution devient nulle ou atteint une valeur constante.
   
   *Exemple*: L'équation de la chaleur $u_t = \alpha^2 u_{xx}$ sur une demi-droite $x > 0$ peut avoir comme condition aux limites que $u(x,t) \to 0$ lorsque $x \to \infty$.

3. **Domaine périodique** : Le domaine est sans limites, mais la fonction solution est périodique. Cela signifie que la solution est la même à des points équidistants.
   
   *Exemple*: L'équation des ondes $u_{tt} = c^2 u_{xx}$ sur un cercle (modélisant une corde vibrante circulaire) requiert que $u(x,t) = u(x + L,t)$ où $L$ est la longueur de la corde.

**Exemples détaillés :**

- **Domaine borné** : Considérons l'équation de Poisson $-\nabla^2 \phi = \rho$ dans un carré avec des conditions de Dirichlet telles que $\phi(x, y) = g(x, y)$ sur les bords du carré. Ici, $\rho$ représente une distribution de charge et $g(x, y)$ est le potentiel électrique sur la frontière.

- **Domaine non borné** : Pour l'équation de Schrödinger non stationnaire $i \hbar \partial_t \psi = -\frac{\hbar^2}{2m} \nabla^2 \psi + V \psi$ dans tout l'espace $\mathbb{R}^3$, on impose souvent que la fonction d'onde $\psi \to 0$ à l'infini pour garantir une probabilité totale finie.

- **Domaine périodique** : Dans le cas de l'équation de convection-diffusion $u_t + c u_x = \alpha u_{xx}$ sur un domaine périodique, on impose $u(x, t) = u(x + P, t)$ où $P$ est la période. Cela peut représenter la concentration d'un polluant dans une rivière circulaire.
