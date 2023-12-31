# Équation de Diffusion
## Forme Générale 1D
$$
\dfrac{\partial}{\partial x}(\alpha \,\phi_{x})=\phi_{t}
$$
Qu'on vois parfois avec un terme source :
$$
\dfrac{\partial}{\partial x}(\alpha \,\phi_{x})=\phi_{t} + F(x,t)
$$
Avec $\alpha>0$ la diffusivité (éventuellement fonction de $x$ et de $\phi$; voir même de $t$). Si $\alpha$ constant :
$$
\boxed{ \alpha \phi_{xx}=\phi_{t}}
$$
$A=\alpha, B=C=0\Rightarrow B^{2}-4AC\Leftrightarrow$ ***parabolique***. De la formule des caractéristiques on trouve qu'il n'y a pas de caractéristiques.

Un problème de diffusion se résout toujours à partir d'une condition initiale $\phi(s,0)=f(s)$. Si le domaine est borné, on doit aussi imposer une condition sur chaque frontière.

## Intégrale Conservée

$$
\dfrac{d}{dt}\int_{a}^{b} \phi \, dx=\int _{a}^{b}\phi_{t} \, dx  =\int _{a}^{b}\alpha \phi_{xx} \, dx =[\alpha \phi_{x}]^{b}_{a}=0
$$

### Énergie

On peut montrer que l'intégrale de $\phi ^2/2$ diminue avec le temps et donc l'énergie.

## Solutions

### Domaine Non Borné

#### Condition Initiale : Gaussienne

Problème non borné et de condition initiale : $\phi(s,0)=\phi_{0}\text{exp}\left( -\dfrac{s^{2}}{b^{2}} \right)$, la solution:
$$
\phi(x,t)=\phi_{0} \dfrac{b}{\sqrt{ b^{2}+4\alpha t }}\text{exp}\left( - \dfrac{x^{2}}{b^{2}+4\alpha t} \right)
$$
D'intégrale :
$$ 
Q 
= \int_{-\infty}^{\infty} \phi(x, t) dx 
= \phi_0 b \int_{-\infty}^{\infty} \dfrac{\text{exp}(-\dfrac{x^2}{b^2 + 4at})}{\sqrt{b^2 + 4at}} dx 
=\phi_{0}b\int _{-\infty}^{+\infty}\text{exp}(-p^{2}) \, dp 
= \phi_0 b \sqrt{\pi}
$$
ne varie pas dans le temps. On peut donc aussi écrire:
$$
\phi(x, t) = \dfrac{Q}{\sqrt{\pi (b^2 + 4at)}} \text{exp}\left(-\dfrac{x^2}{b^2 + 4at}\right)
$$
#### Condition Initiale : Singularité

Si on considère plutôt la diffusion d'une "singularité d'intégrale totale $Q$" et placée à l'origine $x = 0$ en $t = 0$, la solution sera:
$$
\phi(x, t) = \dfrac{Q}{\sqrt{\pi 4at}} e^{-\dfrac{x^2}{4at}} \quad
$$
La condition initiale Gaussienne correspond à une singularité d'intégrale $Q$ qui aurait diffusé pendant un temps$\tau=b^{2}/4\alpha$. Le temps mesuré à partir de la condition initiale Gaussienne est $t$; celui mesuré à partir de la condition initiale singulière est $\tau+t$.

#### Condition Initiale : cas général par convolution

On trouve la solution pour une distribution initiale quelconque $\phi(0,s)=f(s)$ en additionnant la contribution de chaque petit morceaux de $f(s)$ à la solution. Dans le cas à une dimension spatiale, un morceaux infinitésimal correspond à une aire $f(s)ds=dQ(s)$ dont la contribution à la solution est :
$$
\dfrac{dQ(s)}{\sqrt{\pi 4at}} e^{-\dfrac{(x-s)^2}{4at}} = \dfrac{f(s)ds}{\sqrt{\pi 4at}} e^{-\dfrac{(x-s)^2}{4at}}
$$
Qu'on intègre alors pour obtenir : 
$$
\phi(x,t)=\dfrac{1}{\sqrt{\pi 4at}}\int   e^{-\dfrac{(x-s)^2}{4at}} f(s)ds 
$$
On dit que la fonction :
$$
G(r,t)=\dfrac{1}{\sqrt{ 4\pi \alpha t }}e^{-\dfrac{r^2}{4at}}
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
G(r,t)=\dfrac{\exp \left( - \dfrac{r^{2}}{4\alpha t} \right)}{4\pi \alpha t}
$$
En 3D :
$$
G(r,t)=\dfrac{\exp \left( - \dfrac{r^{2}}{4\alpha t} \right)}{(4\pi \alpha t)^{3/2}}
$$

#### Condition Initiale : Domaine Borné Périodique

On résout le problème par séparation de variables. 
On prend par exemple comme condition initiale $\phi(s,0)=\phi_{0}\sin(\pi s/L)$, une fonction de période $2L$. La fonction sera de la forme $\phi(x,t)=g(t)h(x)$, qui dans l'EDP donne :
$$
\alpha \cdot g(t)h''(x)=g'(t)h(x)\Leftrightarrow \alpha\dfrac{h''(x)}{h(x)}=\dfrac{g'(t)}{g(t)}
$$
$2$ fonctions égales pour tout $x$ et $t$ $\Rightarrow$ fonctions constantes
$$
\alpha\dfrac{h''(x)}{h(x)}=\dfrac{g'(t)}{g(t)}=\lambda
$$
Ce qui nous donne un problème de Sturm-Liouville de valeur propre $\dfrac{\lambda}{\alpha}$, (l'important est que ce sont des constantes, pas le nom qu'on leur donne) et d'opérateurs différentiels dérivée première et seconde.
$$
h''(x)-\dfrac{\lambda}{\alpha} h(x)=0
$$
On sait par experience que seul les valeurs pour $\lambda>0$ donneront des solutions triviales, on va donc noter $\dfrac{\lambda}{\alpha}=-k^{2}$. Comme les bornes dont de la forme : $X(-L)=X(L)$ et $X'(-L)=X'(L)$, on sait donc que $h(x)$ sera de la forme :
$$h(x)= \sum_{n=1}^{\infty} A_{n}\sin(k_{n}x)+\sum_{n=0}^{\infty} B_{n}\cos(k_{n}x)$$
Avec $k_{n}=n\pi/L$. On projette maintenant la condition initiale sur la base formée par les solutions du problème de Sturm-Liouville pour trouver les coefficients $A_{n}$. Ceci ce fait avec le produit scalaire $\langle f(x),y_{m} \rangle=\int _{a}^{b}f(x)y_{m}(x)w(x) \, dx$.
$$
A_{n}=\dfrac{1}{L} \int_{-L}^{L}\phi_{0}\sin\left( \dfrac{\pi x}{L} \right)h(x)  \, dx 
$$
Ce qui, par l'orthogonalité entre sinus et cosinus, nous donne :
$$
A_{n}=\left\{\begin{align}
& \phi_{0}\quad\text{si n=1} \\
& \,\,\,0 \quad \text{sinon}
\end{align}
\right. 
\quad B_{n}=0 \quad \Rightarrow \quad h(x)=\phi_{0}\sin\left( \dfrac{\pi x}{L} \right) 
$$
Maintenant qu'on l'expression de $\lambda$ qui est $\lambda=-\alpha\left(\dfrac{ \pi}{L}\right)^{2}$, on peut trouver $g(t) :$
$$
g'(t)=\lambda g(t)\Rightarrow g(t) =\exp\left(-\alpha\left(\dfrac{ \pi}{L}\right)^{2}t\right)
$$
La solution est alors :
$$
\phi(x,t)=\phi_{0}\exp\left(-\alpha\left(\dfrac{ \pi}{L}\right)^{2}t\right)\sin \dfrac{\pi x}{L}
$$
Et on peut montrer que l'intervalle sur une période (ex : $[-L,L]$ ou $[0,2L]$) est conservée, la solution pour une demi période sera la même mais l'intégrale ne sera pas conservée.

Si la condition initiale était plus complexe, par exemple :
$$
\phi(s,0)=\phi_{0}\sum_{n=1}^{N}a_{n}\sin\left( \dfrac{n\pi s}{L} \right)=\phi_{0}\sum_{n=1}^{N}a_{n}\sin\left( k_{n}s \right)
$$
Où $k_{n}s$ est le ***nombre d'onde*** du ***mode*** $n$ et $\lambda_{n}=\dfrac{2\pi}{k_{n}}$ est sa ***longueur d'onde*** (à ne pas confondre avec la valeur propre du problème de Sturm-Liouville). La solution se trouve par superposition des solutions pour chaque mode :
$$
\phi(x,t)=\phi_{0}\sum_{n=1}^{N}a_{n} \exp\left(-\alpha k_{n}^{2}t\right)\sin k_{n}x
$$
On constate que les modes à grand nombre d'onde ($n$ élevé) décroissent beaucoup plus vite que les plus petits modes, les informations à haute fréquence se perdent très rapidement. C'est notamment pour cela qu'on ne peut pas remonter le temps et trouver l'état d'une diffusion dans un temps qui précède la condition initiale.

### Domaine Semi-Infini
On a les condition suivantes sur l'axe $\large t$ positif et $\large x$ positif :
$$
\large 
\left\{

\begin{align}
u(x,0)&=U_{1} \\
u(0,t)&=U_{0}
\end{align}
\right.
$$
On définit alors le changement de variables $\large v(x,t)=u(x,t)-U_{1}$, ce qui nous donne les conditions suivantes sur $\large v$ :
$$
\large 
\left\{

\begin{align}
v(x,0)&=0 \\
v(0,t)&=U_{0}-U_{1}=V_{0}
\end{align}
\right.
$$
La solution peut se trouver en définissant la variable adimensionnelle $\large \eta=\frac{x}{\sqrt{ \alpha t }}$ et en supposant que la solution sera de la forme $\large v(x,t)=f(\eta)$, on a par ailleurs les expression suivantes pour les dérivées de $\large \eta$ :
$$
\large 
\begin{align}
\frac{\partial \eta}{\partial x} &= \frac{1}{\sqrt{ \alpha t }} \\
\frac{\partial \eta}{\partial t}&=\frac{x}{\sqrt{ \alpha }}\left( -\frac{1}{2}t^{-3/2} \right)  \\
&=-\frac{1}{2} \frac{x}{\sqrt{ \alpha }} \frac{1}{\sqrt{ t }} \frac{1}{t} \\
&=-\frac{\eta}{2t}
\end{align}
$$
Ce qui nous permet de développer les dérivées de $\large v$ :
$$
\large 
\begin{align}
\frac{\partial v}{\partial x} &= f'(\eta) \frac{\partial \eta}{\partial x}=f'(\eta) \frac{1}{\sqrt{ \alpha t }} \\ 

\frac{\partial^{2} v}{\partial x^{2}} &= f''(\eta) \frac{\partial \eta}{\partial x}\frac{1}{\sqrt{ \alpha t }}=f''(\eta)\frac{1}{\alpha t}  \\ 

\frac{\partial v}{\partial t}&=f'(\eta)\frac{\partial \eta}{\partial t}=f'(\eta) \left( -\frac{\eta}{2t}\right)
\end{align}
$$
Qu'on substitue maintenant dans l'EDP de diffusion :
$$
\large 
v_{t}=\alpha_{xx} \Rightarrow \, f'(\eta) \left( -\frac{\eta}{2t}\right)=\alpha f''(\eta)\frac{1}{\alpha t}\Rightarrow \boxed{f''(\eta)+\frac{\eta}{2}f'(\eta)=0}  
$$
Ce qui nous donne une EDO ! Pour la résoudre on définit $\large w(\eta)=f'(\eta)$ :
$$
\large 
\begin{align}
w'(\eta)&=-\frac{\eta}{2}w(\eta) \\
\frac{dw}{d \eta}&=-\frac{\eta}{2}w \\
\frac{dw}{w}&=-\frac{\eta}{2}d \eta \\
\log\left( \frac{w(\eta)}{w(0)} \right)&=-\frac{\eta^{2}}{4} \\
\Rightarrow w(\eta)&=w(0)\exp(-\eta^{2}/4) =f'(\eta) \\
\Rightarrow f(\eta)&=w(0)\int^{\eta}_{0}\exp(-s^{2}/4) \, d s+C 
\end{align}
$$
Avec l'unique condition limite on impose $\large V_{0}$ à $\large x=0$ :
$$
\large f(0)=C=V_{0}\Rightarrow f(\eta)=w(0)\int^{\eta}_{0}\exp(-s^{2}/4) \, d s+V_{0}
$$
On a aussi que comme l'intégrale de $\large v$ doit être finie comme on est dans un cas physique et que donc on doit avoir une valeur nulle à l'infini :
$$
\large \lim_{ \eta \to \infty } f(\eta)=w(0)\sqrt{ \pi }+V_{0}  =0\rightarrow w(0)=-V_{0}/\sqrt{ \pi }
$$
Où on a utilisé la valeur de l'intégrale de l'intégrale de Gauss $\large \int_{0}^{\infty} e^{-(x/2)^{2}}  \, dx=\sqrt{ \pi }$.

On peut être satisfait par cette solution, ou on peut poser $\large \nu=\frac{s}{2}$, $\large ds=2d\nu$
$$
\large \Rightarrow f(\eta)=V_{0}\left( 1-\frac{2}{\sqrt{ \pi }} \int^{\eta/2}_{0}\exp(-\nu^{2}) \, d \nu \right) 
$$
On introduit alors les fonction "erreur" et "erreur complémentaires" :
$$
\large \text{erf}(x)\equiv \frac{2}{\sqrt{ \pi }} \int _{ 0 } ^{ x } e^{ -\nu^{2} }  \, d\nu \quad \text{et} \quad \text{erfc}(x)\equiv 1-\text{erf}(x)
$$
Ce qui nous permet d'écrire la solution sous la forme suivante :
$$
\large v(x,t)=f(\eta)=V_{0}\text{erfc}\left( \frac{x}{2\sqrt{ \alpha t }} \right)
$$
$$
\large \boxed{u(x,t)=(U_{0}-U_{1})\text{erfc}\left( \frac{2}{\sqrt{ \alpha t }} \right) + U_{1}}
$$
# Résumé

