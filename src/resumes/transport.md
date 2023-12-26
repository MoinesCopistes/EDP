# L'équation de transport ou de convection

## Forme Générale

$$
\large c(t,x,u) \frac{\partial u(x,y)}{\partial x}+\frac{\partial u(x,y)}{\partial t}=0
$$

C'est une équation homogène et linéaire si $\large c$ ne dépend pas de $\large u$. Comme $\large R=0$, cette équation conserve $\large u$ le long de chaque caractéristique ($\large \frac{du}{dx}=0$ et $\large \frac{du}{dy}=0$ dans les équations de compatibilité)

## Forme Conservative

$$
\large \boxed{ (uc)_{x}+u_{t}=0}\Leftrightarrow c\, u_{x} + u \, c_{x}+u_{t}=0 \Leftrightarrow c\, u_{x} +u_{t}=-u \, c_{x}
$$

L'intégrale de $\large u$ est conservée. Démo :
$$
\large \frac{d}{dt} \int_{a}^{b}u  \, dx =\int_{a}^{b} u_{t} \, dx = \int_{a}^{b} -uc_{x}-cu_{x} \, dx=-\int_{a}^{b} \frac{d(cu)}{dx} \, dx
$$
$$
\large \Leftrightarrow -[cu]^{b}_{a}=0
$$
Ce qui est facilement vérifié sur un domaine périodique et un domaine infini.

## Puit de vitesse

Le cas d'un puit de vitesse pour la forme conservative est donné par :

$$
\large c(x)=c_{\text{max}}-\frac{c_{\text{max}}-c_{\text{min}}}{(1+x^{2}/a^{2})}=\frac{c_{\text{min}}+c_{\text{min}}x^{2}/a^{2}}{(1+x^{2}/a^{2})}
$$

Qui donne une relation implicite pour les caractéristiques $\large I(x)-I(s)=t$ qu'il faut résoudre numériquement. 

## Terme source

On peut aussi avoir une équation de transport écrite sous forme conservative et avec un terme source :
$$
\large \frac{\partial}{\partial x}(cu)+u_{t}=S\Leftrightarrow c\,u_{x}+u_{t}=S-c_{x}u=R
$$
$$
\large \Leftrightarrow c\,v_{x}+v_{t}=cS
$$

## Cas Non-Linéaire

Un cas non-linéaire est celui pour lequel $\large c$ dépend du $\large u$ uniquement. 
$$
\large c(u)\,u_{x}+u_{t}=0
$$
Les caractéristiques sont données par :
$$
\large dx=c(u)dt
$$
Mais comme $\large u$ est conservé le long des caractéristiques parce que l'équation est homogène, on aura alors $\large dx/dt$ constant.

Sa forme conservative est, pour $\large g(u)=\int^{u}c(u')  \, du$ :

$$
\large (g(u))_{x}+u_{t}=0
$$

Dans ce type de problème, il y a une 
- zone d'expansion avec $\large c$ fonction croissante de $\large x$; elles sont donc telles que la pente de la caractéristique en $\large x+dx$ est plus grande que celle en $\large x$ : les caractéristiques ne se croisent pas et la solution est régulière. 
- zone de compression avec $\large c$ fonction décroissante de $\large x$; elles sont donc telles que la pente de la caractéristique en $\large x + dx$ est plus petite que celle en $\large x$: les caractéristiques se croisent.
Après un certain temps fini, la solution deviendra discontinue: l’onde de compression est alors appelée onde de discontinuité (ou onde de choc).
### Équation de Burgers

L'équation de burgers est l'équation de transport non-linéaire conservative la plus classique où $\large c(t,x,u)=u$.

$$
\large u\cdot  u_{x}+u_{y}=0 \Leftrightarrow (u^{2}/2)_{x}+u_{y}=0
$$

On va considérer soit des domaines périodiques ou infinis. Elle est donc homogène, $\large u$ est conservée le long des caractéristiques et les caractéristiques sont de la forme $\large x=s+f(s)t$. On a donc des pentes qui dépendent de $\large s$ et donc du point de départ sur la courbe $\large \Gamma$ ce qui peut poser problème car des caractéristiques peuvent se croiser. 
L'intégrale de $\large u$ sur l'espace est également conservée ainsi que l'énergie (c-à-d l'intégrale de $\large u^{2}/2$). La solution implicite peut s'écrire sous la forme :
$$
\large u(x,t)=f(x-u(x,t)t)
$$

On peut également démontrer que tant qu'il n'y a pas de discontinuité, l'énergie est conservée et le problème est réversible et si il y en a l'énergie diminue et el problème est irréversible.

## Les conditions limites

Pour trouver une solution à une equation de transport, il faut qu'une caractéristique émanant d'une condition limite soit incidente au point en question. On ne pet pas imposer de condition limite où les caractéristiques sont déjà définies par d'autres caractéristiques. Tout dépend donc de la pente des caractéristiques en chaque point et donc d'où nous vient l'information.
Comme autre exemple d'EDP à caractère mixte, citons l'équation des télégraphistes. C'est l'EDP qui régit la chute de potentiel, $v(x,t)$, pour la transmission d'un signal électrique le long d’un câble:
$$
\frac{\partial^2 v}{\partial x^2} - LC \frac{\partial^2 v}{\partial t^2} = (RC + LG) \frac{\partial v}{\partial t} + R G v
$$
avec $R$ la résistance série par unité de longueur, $L$ l’inductance par unité de longueur, $G$ la conductance parallèle par unité de longueur et $C$ la capacité par unité de longueur. Selon le critère mathématique ($B^2 - 4AC > 0$), cette EDP est hyperbolique (= onde). Sa composante de diffusion lui confère aussi un caractère parabolique.
