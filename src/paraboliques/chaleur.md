# Équation de la Chaleur

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

