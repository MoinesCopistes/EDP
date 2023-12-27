# Équation de Diffusion
## Forme Générale 1D
$$
\frac{\partial}{\partial x}(\alpha \,\phi_{x})=\phi_{t}
$$
Qu'on vois parfois avec un terme source :
$$
\frac{\partial}{\partial x}(\alpha \,\phi_{x})=\phi_{t} + F(x,t)
$$
Avec $\alpha>0$ la diffusivité (éventuellement fonction de $x$ et de $\phi$; voir même de $t$). Si $\alpha$ constant :
$$
\boxed{ \alpha \phi_{xx}=\phi_{t}}
$$
$A=\alpha, B=C=0\Rightarrow B^{2}-4AC\Leftrightarrow$ ***parabolique***. De la formule des caractéristiques on trouve qu'il n'y a pas de caractéristiques.

Un problème de diffusion se résout toujours à partir d'une condition initiale $\phi(s,0)=f(s)$. Si le domaine est borné, on doit aussi imposer une condition sur chaque frontière.

## Intégrale Conservée

$$
\frac{d}{dt}\int_{a}^{b} \phi \, dx=\int _{a}^{b}\phi_{t} \, dx  =\int _{a}^{b}\alpha \phi_{xx} \, dx =[\alpha \phi_{x}]^{b}_{a}=0
$$

### Énergie

On peut montrer que l'intégrale de $\phi ^2/2$ diminue avec le temps et donc l'énergie.

## Solutions

### Domaine Non Borné

#### Condition Initiale : Gaussienne

Problème non borné et de condition initiale : $\phi(s,0)=\phi_{0}\text{exp}\left( -\frac{s^{2}}{b^{2}} \right)$, la solution:
$$
\phi(x,t)=\phi_{0} \frac{b}{\sqrt{ b^{2}+4\alpha t }}\text{exp}\left( - \frac{x^{2}}{b^{2}+4\alpha t} \right)
$$
D'intégrale :
$$ 
Q 
= \int_{-\infty}^{\infty} \phi(x, t) dx 
= \phi_0 b \int_{-\infty}^{\infty} \frac{e^{-\frac{x^2}{b^2 + 4at}}}{\sqrt{b^2 + 4at}} dx 
=\phi_{0}b\int _{-\infty}^{+\infty}e^{-p^{2}} \, dp 
= \phi_0 b \sqrt{\pi}
$$
ne varie pas dans le temps. On peut donc aussi écrire:
$$
\phi(x, t) = \frac{Q}{\sqrt{\pi (b^2 + 4at)}} e^{-\dfrac{x^2}{b^2 + 4at}}
$$
#### Condition Initiale : Singularité

Si on considère plutôt la diffusion d'une "singularité d'intégrale totale $Q$" et placée à l'origine $x = 0$ en $t = 0$, la solution sera:
$$
\phi(x, t) = \frac{Q}{\sqrt{\pi 4at}} e^{-\dfrac{x^2}{4at}} \quad
$$
La condition initiale Gaussienne correspond à une singularité d'intégrale $Q$ qui aurait diffusé pendant un temps$\tau=b^{2}/4\alpha$. Le temps mesuré à partir de la condition initiale Gaussienne est $t$; celui mesuré à partir de la condition initiale singulière est $\tau+t$.

#### Condition Initiale : cas général par convolution

On trouve la solution pour une distribution initiale quelconque $\phi(0,s)=f(s)$ en additionnant la contribution de chaque petit morceaux de $f(s)$ à la solution. Dans le cas à une dimension spatiale, un morceaux infinitésimal correspond à une aire $f(s)ds=dQ(s)$ dont la contribution à la solution est :
$$
\frac{dQ(s)}{\sqrt{\pi 4at}} e^{-\dfrac{(x-s)^2}{4at}} = \frac{f(s)ds}{\sqrt{\pi 4at}} e^{-\dfrac{(x-s)^2}{4at}}
$$
Qu'on intègre alors pour obtenir : 
$$
\phi(x,t)=\frac{1}{\sqrt{\pi 4at}}\int   e^{-\dfrac{(x-s)^2}{4at}} f(s)ds 
$$
On dit que la fonction :
$$
G(r,t)=\frac{1}{\sqrt{ 4\pi \alpha t }}e^{-\dfrac{r^2}{4at}}
$$
est la solution élémentaire (i.e. la "fonction de Green") de l'équation de diffusion en domaine non borné 1-D, la solution est alors la convolution entre la condition initiale et la fonction de Green :
$$
\phi(x,t)=\int G(|x-s|,t)f(s)ds\Leftrightarrow \phi=G*f 
$$

##### En 2D/3D

L'équation de diffusion en plusieurs dimensions spatiales est donnée par :
$$
\alpha \nabla^{2}\phi=\phi_{t}
$$
#### Fonctions de Green
En 2D :
$$
G(r,t)=\frac{\exp \left( - \frac{r^{2}}{4\alpha t} \right)}{4\pi \alpha t}
$$
En 3D :
$$
G(r,t)=\frac{\exp \left( - \frac{r^{2}}{4\alpha t} \right)}{(4\pi \alpha t)^{3/2}}
$$

#### Condition Initiale : Domaine Borné Périodique

On résout le problème par séparation de variables. 
On prend par exemple comme condition initiale $\phi(s,0)=\phi_{0}\sin(\pi s/L)$, une fonction de période $2L$. La fonction sera de la forme $\phi(x,t)=g(t)h(x)$, qui dans l'EDP donne :
$$
\alpha \cdot g(t)h''(x)=g'(t)h(x)\Leftrightarrow \alpha\frac{h''(x)}{h(x)}=\frac{g'(t)}{g(t)}
$$
$2$ fonctions égales pour tout $x$ et $t$ $\Rightarrow$ fonctions constantes
$$
\alpha\frac{h''(x)}{h(x)}=\frac{g'(t)}{g(t)}=\lambda
$$
Ce qui nous donne un problème de Sturm-Liouville de valeur propre $\frac{\lambda}{\alpha}$, (l'important est que ce sont des constantes, pas le nom qu'on leur donne) et d'opérateurs différentiels dérivée première et seconde.
$$
h''(x)-\frac{\lambda}{\alpha} h(x)=0
$$
On sait par experience que seul les valeurs pour $\lambda>0$ donneront des solutions triviales, on va donc noter $\frac{\lambda}{\alpha}=-k^{2}$. Comme les bornes dont de la forme : $X(-L)=X(L)$ et $X'(-L)=X'(L)$, on sait donc que $h(x)$ sera de la forme :
$$h(x)= \sum_{n=1}^{\infty} A_{n}\sin(k_{n}x)+\sum_{n=0}^{\infty} B_{n}\cos(k_{n}x)$$
Avec $k_{n}=n\pi/L$. On projette maintenant la condition initiale sur la base formée par les solutions du problème de Sturm-Liouville pour trouver les coefficients $A_{n}$. Ceci ce fait avec le produit scalaire $\langle f(x),y_{m} \rangle=\int _{a}^{b}f(x)y_{m}(x)w(x) \, dx$.
$$
A_{n}=\frac{1}{L} \int_{-L}^{L}\phi_{0}\sin\left( \frac{\pi x}{L} \right)h(x)  \, dx 
$$
Ce qui, par l'orthogonalité entre sinus et cosinus, nous donne :
$$
A_{n}=\left\{\begin{align}
& \phi_{0}\quad\text{si n=1} \\
& \,\,\,0 \quad \text{sinon}
\end{align}
\right. 
\quad B_{n}=0 \quad \Rightarrow \quad h(x)=\phi_{0}\sin\left( \frac{\pi x}{L} \right) 
$$
Maintenant qu'on l'expression de $\lambda$ qui est $\lambda=-\alpha\left(\frac{ \pi}{L}\right)^{2}$, on peut trouver $g(t) :$
$$
g'(t)=\lambda g(t)\Rightarrow g(t) =\exp\left(-\alpha\left(\frac{ \pi}{L}\right)^{2}t\right)
$$
La solution est alors :
$$
\phi(x,t)=\phi_{0}\exp\left(-\alpha\left(\frac{ \pi}{L}\right)^{2}t\right)\sin \frac{\pi x}{L}
$$
Et on peut montrer que l'intervalle sur une période (ex : $[-L,L]$ ou $[0,2L]$) est conservée, la solution pour une demi période sera la même mais l'intégrale ne sera pas conservée.

Si la condition initiale était plus complexe, par exemple :
$$
\phi(s,0)=\phi_{0}\sum_{n=1}^{N}a_{n}\sin\left( \frac{n\pi s}{L} \right)=\phi_{0}\sum_{n=1}^{N}a_{n}\sin\left( k_{n}s \right)
$$
Où $k_{n}s$ est le ***nombre d'onde*** du ***mode*** $n$ et $\lambda_{n}=\frac{2\pi}{k_{n}}$ est sa ***longueur d'onde*** (à ne pas confondre avec la valeur propre du problème de Sturm-Liouville). La solution se trouve par superposition des solutions pour chaque mode :
$$
\phi(x,t)=\phi_{0}\sum_{n=1}^{N}a_{n} \exp\left(-\alpha k_{n}^{2}t\right)\sin k_{n}x
$$
On constate que les modes à grand nombre d'onde ($n$ élevé) décroissent beaucoup plus vite que les plus petits modes, les informations à haute fréquence se perdent très rapidement. C'est notamment pour cela qu'on ne peut pas remonter le temps et trouver l'état d'une diffusion dans un temps qui précède la condition initiale.



# Résumé

