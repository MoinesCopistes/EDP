# Équation de Poisson
## Forme Générale 2D
$$
\phi_{xx}+\phi_{yy}=F\Leftrightarrow \nabla^{2}\phi=F
$$
Avec $A=1,B=0,C=1,R=F\Rightarrow$ ***Elliptique***. Les solution des équations des caractéristiques sont imaginaires, on dit donc qu'il n'y a pas de caractéristiques.
On a aussi :
$$
\dfrac{\partial}{\partial x}(A\phi_{x})+\dfrac{\partial}{\partial y}(A\phi_{y})=F\Leftrightarrow \nabla \cdot (A\nabla \phi)=F
$$
Avec $A$ qui peut dépendre de $x,y$ et parfois $\phi$ est ***l'équation de Poisson généralisée***.
Par le théorème de la divergence :
$$

\begin{align}
\int _{\Omega}F \, dxdy  
=& \int _{\Omega}\dfrac{\partial}{\partial x}(A\phi_{x})+\dfrac{\partial}{\partial y}(A\phi_{y}) \, dxdy  \\
=& \oint_{\partial \Omega} A(\phi_{x}\,n_{x}+\phi_{y}\,n_{y})dl \\
=& \oint_{\partial \Omega} A(s) \dfrac{\partial\phi}{\partial n}(s) dl(s)

\end{align}
$$
On a donc que le flux pondéré sortant d'un domaine pour un problème de poisson est égal à l'intégrale du terme source sur ce domaine.

Les problèmes elliptiques doivent être résolus de manière globale: tous les points influencent tous les points! Ces problèmes sont toujours résolus sur un domaine physique $\Omega$. Si le domaine est borné, il faut donner une condition en tout point de sa frontière $\partial \Omega$ paramétrisée par $s$. On y prescrit soir la fonction $\phi(s)$ (Dirichlet), soit la dérivée normale$\dfrac{\partial \phi}{\partial n}(s)$ (Neumann), soit une condition mixte (Robin).

## Solutions
### Non Borné
#### Singularité
On considère le cas classique $\nabla^{2}\phi=F$ de singularité totale $Q$ placée à l'origine. On a donc une équation de Poisson avec comme terme source la singularité et comme $F=0$ en tout point sauf l'origine, on a une équation de Laplace partout sauf à l'origine. On va résoudre la problème en coordonnées polaires, le Laplacien 2D sous forme polaire donne :
$$
\nabla^{2}\phi (r,t)=\dfrac{1}{r} \dfrac{\partial}{\partial r}(r\,\phi_{r})+\dfrac{1}{r^{2}}\,\phi_{\theta \theta}=0
$$
Par la symétrie du problème, on sait que $\phi$ ne dépend pas de $\theta$, l'équation se réduit donc à :
$$
\dfrac{1}{r} \dfrac{d}{dr}(r\,\phi_{r})=0 \Rightarrow r\phi_{r}=C\Leftrightarrow \dfrac{d\phi}{dr}=\dfrac{C}{r}  
$$
On peut déterminer $C$ par le résultat ci-dessus qui montre que l'intégrale du terme source donne le flux pondéré sortant de la surface d'intégration, comme dans ce cas si on a $A=1$ et que dans le cas d'un cercle $\phi_{n}=\phi_{r}$ :
$$
\int_{\Omega} F  \, dxdy= \oint_{\partial \Omega} A(s) \dfrac{\partial\phi}{\partial n}(s) dl(s)=\int_{C}\phi_{r}  \, dxdy=\int _{0}^{2\pi} \dfrac{C}{\sqrt{ \cos(t)^{2}+\sin(t)^{2} }}|(-\sin(t),\cos(t))| \, dt=2\pi C  
$$
$$\Rightarrow C=Q/2\pi \Rightarrow \dfrac{d\phi}{dr}=\dfrac{Q}{2\pi r}\Rightarrow \phi(r)=\dfrac{Q}{2\pi}\ln\left( \dfrac{r}{L} \right)  $$
Avec $L$ une constante de longueur arbitraire (les profs n'aiment pas trop voir des termes avec des unités dans des fonctions comme $\ln(\dots)$).
#### Distribution Répartie
On considère le cas :
$$
F(x,y)=F(r)=\dfrac{Q}{\pi} \dfrac{\sigma^{2}}{(r^{2}+\sigma^{2})^{2}}
$$
Dont on peut vérifier que l'intégrale totale est $Q$ :
$$\int \int F(x, y) \, dx \, dy = \int_{0}^{2\pi} \int_{0}^{\infty} F(r) \, r \, dr \, d\theta = 2\pi \int_{0}^{\infty} F(r) \, r \, dr  $$
$$
\Rightarrow 2\pi \cdot \dfrac{Q\sigma^{2}}{\pi}\int _{0}^{\infty} \dfrac{r}{(r^{2}+\sigma^{2})^{2}} \, dr=2Q\sigma^{2}\left[  -\dfrac{1}{2}(r^{2}+\sigma^{2})^{-1}   \right]^{\infty}_{0}=  2Q\sigma^{2}\cdot \dfrac{1}{2\sigma^{2}}=Q
$$
Et la solution trouve par intégration parce que l'équation ne dépend que de $r$ :
$$
\phi(r)=\dfrac{Q}{4\pi}\ln\left( \dfrac{r^{2}+\sigma^{2}}{L^{2}} \right)
$$
Avec $L$ une constante de longueur arbitraire (les profs n'aiment pas trop voir des termes avec des unités dans des fonctions comme $\ln(\dots)$).

Note : Le cas d'une singularité d'intégrale $Q$ correspond à la limite $\sigma \rightarrow {0}$ de la distribution répartie
#### Distribution Gaussienne
On considère le cas :
$$
F(r)=\dfrac{Q}{\pi \sigma^{2}}\exp\left( -\dfrac{r^{2}}{\sigma^{2}} \right)
$$
Dont on peut encore vérifier qu'elle est d'intégrale $Q$ et dont la solution est encore obtenue par intégration :
$$
\phi(r)=\dfrac{Q}{2\pi}\left[\ln\left( \dfrac{r}{L}+\dfrac{1}{2}E_{1}\left( \dfrac{r^{2}}{\sigma^{2}} \right) \right)\right]
$$
Où $E_{1}(q)=\int^{\infty}_{q} \dfrac{e^{-p}}{p} \, dp$ avec $q>0$. Le cas d'une singularité d'intégrale $Q$ correspond aussi à la limite $\sigma \rightarrow0$ de la distribution Gaussienne d'intégrale $Q$.

On peut obtenir une singularité d'intégrale $Q$ comme la limite de n'importe quelle distribution régulière d'intégrale $Q$. Elle ne doit même pas être continue, elle doit just être intégrable.

#### Distribution Chapeau
$$
F(r)=\dfrac{Q}{\pi \sigma^{2}}
$$
TODO : Considérer la distribution chapeau pour $0\leq r\leq \sigma$ et $F(r)=0$ pour $r>\sigma$, et obtenir la solution $\phi(r)$ correspondante pour $0\leq r\leq \sigma$. Pour $r> \sigma$, on obtient que $\phi(r)=\dfrac{Q}{2\pi}\ln\left( \dfrac{r}{L} \right)$. Donc, au dela de la distance $\sigma$, la solution est exactment la même que celle produite par la singularité

#### Superposition
On peut aussi additionner des solutions. Par exemple, si on place une singularité d’intégrale $Q$ en $x = x_{0}$ et une singularité d’intégrale $−Q$ en $x = −x_{0}$, on obtient le champ induit par un dipôle :
$$\phi(x, y) = \dfrac{Q}{4\pi} \log\left(\dfrac{(x - x_0)^2 + y^2}{L^2}\right) - \dfrac{Q}{4\pi} \log\left(\dfrac{(x + x_0)^2 + y^2}{L^2}\right) = \dfrac{Q}{4\pi} \log\left(\dfrac{(x - x_0)^2 + y^2}{(x + x_0)^2 + y^2}\right) $$
#### Cas Général par Convolution
On trouve la solution pour une distribution quelconque $F$ en additionnant la contribution de chaque petit morceaux de $F(x,y)$ à la solution. Dans le cas à deux dimensions spatiales, un morceaux infinitésimal correspond à une aire $F(x',y')dx'dy'=dQ(x',y')$ dont la contribution à la solution est :
$$\phi(x, y) = \dfrac{1}{4\pi} \ln\left(\dfrac{(x - x')^2 + (y - y')^2}{L^2}\right) F(x', y') \, dx' \, dy'. $$
En en intégrant les contributions de toutes les parties élémentaires on obtient :
$$\phi(x, y) = \dfrac{1}{4\pi} \int \int \ln\left(\dfrac{(x - x')^2 + (y - y')^2}{L^2}\right) F(x', y') \, dx' \, dy'. $$ On dit que la fonction : $$G(r) = \dfrac{1}{2\pi} \ln\left(\dfrac{r}{L}\right) = \dfrac{1}{4\pi} \ln\left(\dfrac{r^2}{L^2}\right) $$Est la solution élémentaire ou fonction de Green de l'équation de Poisson en domaine non-borné 2D,  la solution est alors la convolution entre la condition initiale et la fonction de Green.
$$\phi(x, y) = \int \int G\left( \sqrt{(x - x')^2 + (y - y')^2} \right) F(x', y') \, dx' \, dy' \quad \Leftrightarrow \quad \phi = G * F. $$
#### Fonctions de Green 3D
En 3D :
$$
G(r)=-\dfrac{1}{4\pi r}
$$



## Résumé
- Le flux pondéré sortant d'un domaine pour un problème de poisson est égal à l'intégrale du terme source sur ce domaine.
- Un problème de Poisson sur un domaine avec des conditions limites de Dirichlet a une solution unique.
- Un extremum ne se trouvera jamais à l'intérieur d'un domaine d'un problème de Poisson.


## Sources
https://www.damtp.cam.ac.uk/user/reh10/lectures/nst-mmii-chapter2.pdf