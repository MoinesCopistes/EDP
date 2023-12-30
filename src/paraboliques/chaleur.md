# Équation de la Chaleur
## Dérivation
### Dérivation 1
On considère un barreau droit de longueur $\large L$ et de section $\large A$. On définit $\large e(x,t)\,[J/m^{3}]$, sa densité d'énergie par unité de volume. On étudie ensuite l'énergie thermique d'une portion $\large [x,x+\Delta x]$ du barreau :
$$
\large E(x,t)\approx A\,e(x,t)\, \Delta x \,\,\,\,\,[J]
$$
Elle peut varier du à un flux $\large \phi(x,t)[W/m^{2}]$ entrant ou sortant ou une source d'énergie thermique $\large Q(x,t)\,[W]$ dans la portion. Si on définit le flux comme étant positif si il s'écoule vers la droite alors $\large \phi(x,t)>0$ si un flux net entre dans le barreau et $\large \phi(x+\Delta x,t)>0$ si un flux net sort du barreau. La conservation de l'énergie s'écrit alors :
$$
\large \frac{\partial}{\partial t}[A\,e(x,t)\,\Delta x]\approx\phi(x,t)\,A-\phi(x+\Delta x,t)\,A+Q(x,t)\,A\,\Delta x
$$
Parce que la variation d'énergie interne correspond à l'énergie qui entre en $\large x$ moins celle qui sors en $\large x+\Delta x$ plus l'apport de la source. Cette équation devient de plus en plus précise quand $\large \Delta x\rightarrow0$. Si on divise par $\large A\,\Delta x$ :
$$
\large \frac{\partial e}{\partial t} \approx- \frac{\phi(x+\Delta x,t)-\phi(x,t)}{\Delta x}+Q(x,t)
$$
$$
\large \Rightarrow \lim_{ \Delta x \to 0 } \frac{\partial e}{\partial t}=\lim_{ \Delta x \to 0 }-  \frac{\phi(x+\Delta x,t)-\phi(x,t)}{\Delta x}+Q(x,t)
$$
$$
\large \boxed{e_{t}=-\phi_{x}+Q}
$$
### Dérivation 2
Considérons un barreau de longueur finie $\large b-a$. La conservation de l'énergie pour cette portion s'écrit (en ayant supprimé les $\large A$) :
$$
\large \frac{d}{dt} \underbrace{ \int_{a}^{b}e \, dx}_{f(t)}=\phi(a,t)-\phi(b,t)+\int_{a}^{b}Q(x,t)  \, dx  
$$
Pour $\large \phi$ continument dérivable, on a l'identité :
$$
\large \phi(a,t)-\phi(b,t)=-\int_{a}^{b}\phi_{x}  \, dx 
$$
On peut alors réécrire la conservation de l'énergie :
$$
\large \int_{a}^{b}e_{x}+\phi_{x}-Q  \, dx=0 
$$
Comme l'intégrale doit être nulle pour tout $\large a,b$ (la conservation de l'énergie est valable partout et toujours), l'intégrant est identiquement nul.
$$
\large \boxed{e_{t}=-\phi_{x}+Q}
$$
### Température
On peut lier la densité d'énergie thermique à la température en utilisant la chaleur spécifique $\large c\,[J/(\text{kg}\cdot \text{K})]$ et la masse volumique de la portion du barreau qu'on étudie :
$$
\large e(x,t)=c(x)\rho(x)u(x,t)
$$
Ce qui nous donne une nouvelle forme pour l'équation de la chaleur :
$$
\large c(x)\rho(x)\,u_{x}=-\phi_{x}+Q
$$
Il faut maintenant lier le flux de chaleur et la température, on remercie M. Fourier pour la relation suivante :
$$
\large \phi(x,t)=-K_{0}\,u_{x}
$$
Le signe - indique que le flux d'énergie va dans le sens opposé du gradient de température et c'est normal parce que l'énergie va des zones à haute température vers les zones à basse température. $\large K_{0}\,[W/(m\cdot \text{K})]$ est la conductivité thermique du matériau. Elle représente la quantité de chaleur transférée par unité de surface et par une unité de temps sous un gradient de température de 1 degré par mètre.
On substitue :
$$
\large c(x)\rho(x)\,u_{x}=\frac{\partial}{\partial x}\left( K_{0}\frac{\partial u}{\partial x} \right)+Q
$$
En supposant $\large c,\rho ,K_{0}$ constant et en définissant la diffusivité thermique $\large \alpha=K_{0}/(\rho \cdot c)\,[\text{K}/m^{2}]$ et qu'aucune source thermique n'est présente :
$$
\large \boxed{u_{t}=\alpha\,u_{xx}}
$$
Qui est : ***parabolique***, ***linéaire*** et ***homogène***.

## Conditions Limites
1. On peut imposer la température en un point par exemple à $\large x=0$ :
   $$\large u(0,t)=u_{0}(t)$$
   C'est une ***condition limite de Dirichlet***.
2. On peut aussi imposer le flux de chaleur à un certain point par exemple à $\large x=0$ :
   $$\large -K_{0}(0)\,u_{x}(0,t)=\phi_{0}(t)$$
   On peut prendre l'exemple du barreau parfaitement isolé, on aura un flux nul. C'est une ***condition limite de Neumann***.
3. Condition limite de convection : on imagine une parois avec d'un côté un fluide et de l'autre l'objet dont on étudie la température, la température du fluide avoisinant la paroi sera impactée par la température du système à la paroi et la température du fluide à une distance lointaine donnée $\large u_{\infty}$, on peut modéliser ces influences par l'équation suivante :
   $$\large -K_{0}(0)\,u_{x}(0,t)=-H(u(0,t)-u_{\infty})$$
   Qui donne le flux en fonction des températures du fluide lointain et du système à la paroi et d'un facteur $\large H$. Il faut faire attention aux signes ! Si la paroi se trouvait à droite du système on devrait changer de signe. La condition fait intervenir la fonction et sa dérivée, c'est donc une ***condition limite de Robin***.


Pour que le problème du transfert de chaleur soit bien posé, une des 3 conditions limites citées doit être imposée sur chaque frontière du domaine. On trouvera également qu'on ne peut pas imposer la température et la flux en même temps car cela mène à un problème mal posé.


## Régime Stationnaire
Avant de trouver les solutions à un temps $\large t$ quelconque, on va regarder ce qu'il se passe en régime stationnaire.
### Température Fixée Aux Extrémités
La dérivée par rapport au temps est nulle donc l'équation devient simplement :
$$
\large u_{xx}=0\Rightarrow u_{s}(x)=a+bx 
$$
On peut déterminer les constantes avec les conditions limites : $\large u_{s}(0)=a=T_{1}$ et $\large u_{s}(L)=a+bL=T_{1}+bL=T_{2}$
$$
\large \Rightarrow u_{s}(x)=T_{1}+\frac{T_{2}-T_{1}}{L}x 
$$
La solution est donc indépendante d'une quelconque condition initiale et prend la forme d'une droite.
### Flux Fixé Aux Extrémités
On cherche la solution de :
$$
\large  u_{t}=\alpha u_{xx};\underbrace{u(x,0)=u_{0}(x)}_{\text{Condition Initiale}};\underbrace{-K_{0}\,u_{x}(0,t)=\phi_{0}}_{\text{Neumann à Gauche}};\underbrace{-K_{0}\,u_{x}(L,t)=\phi_{L}}_{\text{Neumann à droite}}
$$
On peut montrer que l'existance d'une solution au régime stationnaire dépend de l'équilibre des flux des $\large 2$ côtés, il y aura une solution uniquement quand $\large \phi_{0}=\phi_{L}$ :
$$
\large u_{s}(x)=\bar{u}-\frac{\phi_{0}}{K_{0}}\left( x-\frac{L}{2} \right)
$$
Si les extrémités sont isolées, alors la température stationnaire $\large u_{s}$ est une constante. Avec $\large \bar{u}$ :
$$
	\large \bar{u}=\frac{1}{L} \int_{0}^{L}u_{0}  \, dx 
$$

## 2D/3D
### Dérivation
Soit un domaine $\large \Omega \subset R^{d}|d\in\{2,3\}$ de frontière orientable $\large \Gamma$ dont la normale extérieure est notée $\large \overrightarrow{n}$. L'énergie thermique est donnée par :
$$
\large E=\int_{\Omega}\rho\,c\,u \, dv 
$$
Le flux à travers $\large \Gamma$ est :
$$
\large -\int_{\Gamma}\overrightarrow{\phi}\cdot \overrightarrow{n}  \, ds 
$$
Le signe − est du au fait que la normale extérieure a été choisie, le flux est positif si de la chaleur s’échappe du domaine et inversement. On mentionne aussi les sources volumiques de chaleur de quantité totale de chaleur produite :
$$
\large \int_{\Omega}Q  \, dv\,\,\,\,\text{[W]} 
$$
On a alors, par la conservation de l'énergie et par le théorème de la divergence :
$$
\large \int_{\Omega}\rho\,c\,u \, dv = -\int_{\Gamma}\overrightarrow{\phi}\cdot \overrightarrow{n}  \, ds +\int_{\Omega}Q  \, dv
$$
$$
\large \Leftrightarrow \int _{\Omega}\left( \frac{\partial}{\partial t}(\rho\,c\,u)+\nabla \cdot \overrightarrow{\phi}-Q \right) \, dv=0 \Leftrightarrow \frac{\partial}{\partial t}(\rho\,c\,u)=-\nabla \cdot \overrightarrow{\phi}+Q
$$
On remercie encore une fois M. Fourier pour la relation suivante :
$$
\large \vec{\phi}(\vec{x},t)=-K_{0}\nabla u
$$
$$
\large \Leftrightarrow \frac{\partial}{\partial t}(\rho cu)=\nabla \cdot (K_{0}\nabla u)+Q
$$
Si les paramètres sont constants :
$$
\large\boxed{u_{t}=\alpha \nabla^{2}u+\frac{Q}{\rho\,c}} 
$$
Les conditions limites/initiales s'étendent facilement au cas 2D/3D et on note que si on divise la frontière en 3 composantes en fonction du type de condition limite $\large \Gamma=\Gamma_{D}\cup \Gamma_{N}\cup \Gamma_{R}$, on doit avoir $\large \Gamma_{D}\cap \Gamma_{N}=\Gamma_{D}\cap \Gamma_{R}=\Gamma_{R}\cap \Gamma_{N}=\emptyset$

Dirichlet $\large \Gamma_{D}$ :
$$
\large u(\vec{x},t)=u_{0}(\vec{x},t)\quad \vec{x}\in\Gamma_{d}
$$
Neumann $\large \Gamma_{N}$ :
$$
\large -K_{0}\nabla u\cdot \vec{n}=\phi_{0}(\vec{x},t) \quad \vec{x}\in\Gamma_{N}
$$
Robin $\large \Gamma_{R}$ :
$$
\large \large -K_{0}\nabla u\cdot  \vec{n}=-H(u(\vec{x},t)-u_{\infty}) \quad \vec{x}\in\Gamma_{R}
$$




