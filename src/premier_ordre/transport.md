# Équation de Transport

# L'équation de transport ou de convection

## Forme Générale

$$
c(t,x,u) \frac{\partial u(x,y)}{\partial x}+\frac{\partial u(x,y)}{\partial t}=0
$$

C'est une équation homogène et linéaire si $c$ ne dépend pas de $u$. Comme $R=0$, cette équation conserve $u$ le long de chaque caractéristique ($\frac{du}{dx}=0$ et $\frac{du}{dy}=0$ dans les équations de compatibilité)

## Forme Conservative

$$
\boxed{ (uc)_{x}+u_{t}=0}\Leftrightarrow c\, u_{x} + u \, c_{x}+u_{t}=0 \Leftrightarrow c\, u_{x} +u_{t}=-u \, c_{x}
$$

L'intégrale de $u$ est conservée. Démo :
$$
\frac{d}{dt} \int_{a}^{b}u  \, dx =\int_{a}^{b} u_{t} \, dx = \int_{a}^{b} -uc_{x}-cu_{x} \, dx=-\int_{a}^{b} \frac{d(cu)}{dx} \, dx
$$
$$
\Leftrightarrow -[cu]^{b}_{a}=0
$$
Ce qui est facilement vérifié sur un domaine périodique et un domaine infini. Cependant

## Puit de vitesse

Le cas d'un puit de vitesse pour la forme conservative est donné par :

$$
c(x)=c_{\text{max}}-\frac{c_{\text{max}}-c_{\text{min}}}{(1+x^{2}/a^{2})}=\frac{c_{\text{min}}+c_{\text{min}}x^{2}/a^{2}}{(1+x^{2}/a^{2})}
$$

Qui donne une relation implicite pour les caractéristiques $I(x)-I(s)=t$ qu'il faut résoudre numériquement. 

## Terme source

On peut aussi avoir une équation de transport écrite sous forme conservative et avec un terme source :
$$
\frac{\partial}{\partial x}(cu)+u_{t}=S\Leftrightarrow c\,u_{x}+u_{t}=S-c_{x}u=R
$$
$$
\Leftrightarrow c\,v_{x}+v_{t}=cS
$$

## Cas Non-Linéaire

Un cas non-linéaire est celui pour lequel $c$ dépend du $u$ uniquement. 
$$
c(u)\,u_{x}+u_{t}=0
$$
Les caractéristiques sont données par :
$$
dx=c(u)dt
$$
Mais comme $u$ est conservé le long des caractéristiques parce que l'équation est homogène, on aura alors $dx/dt$ constant.

Sa forme conservative est, pour $g(u)=\int^{u}c(u')  \, du$ :

$$
(g(u))_{x}+u_{t}=0
$$

Dans ce type de problème, il y a une 
- zone d'expansion avec $c$ fonction croissante de $x$; elles sont donc telles que la pente de la caractéristique en $x+dx$ est plus grande que celle en $x$ : les caractéristiques ne se croisent pas et la solution est régulière. 
- zone de compression avec $c$ fonction décroissante de $x$; elles sont donc telles que la pente de la caractéristique en $x + dx$ est plus petite que celle en $x$: les caractéristiques se croisent.
Après un certain temps fini, la solution deviendra discontinue: l’onde de compression est alors appelée onde de discontinuité (ou onde de choc).
### Équation de Burgers

L'équation de burgers est l'équation de transport non-linéaire conservative la plus classique où $c(t,x,u)=u$.

$$
u\cdot  u_{x}+u_{y}=0 \Leftrightarrow (u^{2}/2)_{x}+u_{y}=0
$$

On va considérer soit des domaines périodiques ou infinis. Elle est donc homogène, $u$ est conservée le long des caractéristiques et les caractéristiques sont de la forme $x=s+f(s)t$. On a donc des pentes qui dépendent de $s$ et donc du point de départ sur la courbe $\Gamma$ ce qui peut poser problème car des caractéristiques peuvent se croiser. 
L'intégrale de $u$ sur l'espace est également conservée ainsi que l'énergie (c-à-d l'intégrale de $u^{2}/2$). La solution implicite peut s'écrire sous la forme :
$$
u(x,t)=f(x-u(x,t)t)
$$

On peut également démontrer que tant qu'il n'y a pas de discontinuité, l'énergie est conservée et le problème est réversible et si il y en a l'énergie diminue et el problème est irréversible.

## Les conditions limites

Pour trouver une solution à une equation de transport, il faut qu'une caractéristique émanant d'une condition limite soit incidente au point en question. On ne pet pas imposer de condition limite où les caractéristiques sont déjà définies par d'autres caractéristiques. Tout dépend donc de la pente des caractéristiques en chaque point et donc d'où nous vient l'information.
Comme autre exemple d'EDP à caractère mixte, citons l'équation des télégraphistes. C'est l'EDP qui régit la chute de potentiel, $v(x,t)$, pour la transmission d'un signal électrique le long d’un câble:
$$
\frac{\partial^2 v}{\partial x^2} - LC \frac{\partial^2 v}{\partial t^2} = (RC + LG) \frac{\partial v}{\partial t} + R G v
$$
avec $R$ la résistance série par unité de longueur, $L$ l’inductance par unité de longueur, $G$ la conductance parallèle par unité de longueur et $C$ la capacité par unité de longueur. Selon le critère mathématique ($B^2 - 4AC > 0$), cette EDP est hyperbolique (= onde). Sa composante de diffusion lui confère aussi un caractère parabolique.
