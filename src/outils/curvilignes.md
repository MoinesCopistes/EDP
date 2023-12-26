# Coordonnées Curvilignes et Opérateurs Différentiels

Soit une fonction $f(x_{1},x_{2},x_{3})$ continûment dérivable et la fonction composée $f(x_{1}(\overrightarrow{q}),x_{2}(\overrightarrow{q}),x_{3}(\overrightarrow{q}))$.

Soit une fonction $f(u(x,y,x),v(x,y,z),w(x,y,x))$ dont on cherche le gradient, la divergence et le Laplacien, on pense par exemple à $f(\theta(x,y,z),\phi(x,y,z),z(x,y,z))$ pour des coordonnées cylindriques, on connait déjà l'expression des différents opérateurs différentiels en coordonnées cartésiennes mais il est souvent plus commode de travailler en coordonnées curvilignes et donc on aimerait avoir leur expressions sous cette forme. 

**Notation :**
Pour un vecteur infinitésimal $dr=(dx,dy,dz)$, on définit les ***facteurs d'échelle*** :
$$
h_{u}\equiv\left| \frac{\partial r}{\partial u} \right| \quad h_{v}\equiv\left| \frac{\partial r}{\partial v} \right| \quad h_{w}\equiv\left| \frac{\partial r}{\partial w} \right|
$$
Et $\hat{u},\hat{v},\hat{w}$ des ***vecteurs unités*** le long de $\partial r/\partial u$,  $\partial r/\partial v$, $\partial r/\partial w$. Et comme :
$$
dr=\frac{\partial r}{\partial u}du+\frac{\partial r}{\partial v}dv+\frac{\partial r}{\partial w}dw
$$
On trouve :
$$
dr=h_{u}\,du\,\hat{u}+h_{v}\,dv\,\hat{v}+h_{w}\,dw\,\hat{w}
$$
#### Exemple : Coordonnées Polaires
$$

\left\{
\begin{align}
x=r\cos(\theta) \\
y=r\sin(\theta)
\end{align}
\right.
$$
On étudie donc une fonction $f(r,\theta)$.
Pour trouver $dr \equiv(dx,dy)$ on calcule d'abord $h_{r}$ et $h(\theta)$ :
$$\large
h_r = \left| \frac{\partial (x, y)}{\partial (r, r)} \right| = \sqrt{\cos^2(\theta) + \sin^2(\theta)} = 1
$$
$$\large
h_\theta = \left| \frac{\partial (x, y)}{\partial (\theta, \theta)} \right| = \sqrt{[-r \sin(\theta)]^2 + [r \cos(\theta)]^2} = r
$$
$dr$ est donc donné par :
$$\large
dr = dr \, \hat{r} + r \, d\theta \, \hat{\theta}
$$
On peut on déduire l'expression de plusieurs quantités intéressantes :

***L'élément de ligne 2D :*** $dl \equiv \sqrt{ dr\cdot dr }=\sqrt{ (dr)^{2}+r^{2}(d\theta)^{2} }$

***L'élément de surface :*** $dS=h_{r}\,h_{\theta}\,dr\,d\theta=r\,dr\,d\theta$

Et en 3D :

***L'élément de ligne 3D :*** $dl \equiv \sqrt{ dr\cdot dr }=\sqrt{ (h_{u}\,du)^{2}+(h_{v}\,dv)^{2}+(h_{w}\,dw)^{2} }$

***L'élément de volume :*** $dV = \left[ (\hat{u} \cdot d\mathbf{r})\hat{u} \right] \cdot \left\{ \left[ (\hat{v} \cdot d\mathbf{r})\hat{v} \right] \times \left[ (\hat{w} \cdot d\mathbf{r})\hat{w} \right] \right\} = h_uh_vh_w \, du \, dv \, dw$

## Gradient
$$
\nabla f(u,v,w)=\frac{f_{u}\hat{u}}{h_{u}}+\frac{f_{v}\hat{v}}{h_{v}}+\frac{f_{w}\hat{w}}{h_{w}}
$$
J'utilise la notation $\frac{\partial f}{\partial u}=f_{u}$ quand il n'y a pas trop de risque de confusion.
## Divergence
$$\nabla \cdot \overrightarrow{A}(u,v,w) = \frac{1}{h_uh_vh_w} \left[ \frac{\partial (A_uh_vh_w)}{\partial u} + \frac{\partial (A_vh_uh_w)}{\partial v} + \frac{\partial (A_wh_uh_v)}{\partial w} \right] $$
## Laplacien
$$\nabla^2f(u,v,w) = \frac{1}{h_uh_vh_w} \left[ \frac{\partial}{\partial u} \left( \frac{h_vh_w}{h_u} \phi_{u} \right) + \frac{\partial}{\partial v} \left( \frac{h_uh_w}{h_v} \phi_{v} \right) + \frac{\partial}{\partial w} \left( \frac{h_uh_v}{h_w} \phi_{w} \right) \right] $$
## Polaire 2D
$$

\left\{
\begin{align}
x=r\cos(\theta) \\
y=r\sin(\theta)
\end{align}
\right.
$$
***Gradient*** d'une fonction scalaire $\phi$ :
$$
\nabla \phi=\phi_{r}\,\hat{r}+\frac{1}{r}\phi_{\theta}\,\hat{\theta}
$$
***Divergence*** d'un champ vectoriel $\mathbf{v}=v_{1}\hat{r}+v_{2}\hat{\theta}$
$$
\nabla \cdot \mathbf{v}=\frac{1}{r} \frac{\partial}{\partial r}(rv_{1})+\frac{1}{r} \frac{\partial v_{\theta}}{\partial \theta}
$$
***Laplacien*** d'une fonction scalaire $\phi$ :
$$
\nabla^{2}\phi=\frac{1}{r} \frac{\partial}{\partial r}(r\,\phi_{r})+\frac{1}{r^{2}}\,\phi_{\theta \theta}
$$

## Coordonnées Sphériques
$$

\left\{
\begin{align}
x&=r\sin(\theta)\cos(\phi) \\
y&=r\cos(\theta)\sin(\phi) \\
z&=r\cos(\theta)
\end{align}
\right.
$$
On trouve :
$$ 
\begin{align}
h_r &= \sqrt{\left( \frac{\partial x}{\partial r} \right)^2 + \left( \frac{\partial y}{\partial r} \right)^2 + \left( \frac{\partial z}{\partial r} \right)^2} = \sqrt{\sin^2(\theta) \cos^2(\phi) + \sin^2(\theta) \cos^2(\phi) + \cos^2(\theta)} = 1 \\
h_\theta &= \sqrt{\left( \frac{\partial x}{\partial \theta} \right)^2 + \left( \frac{\partial y}{\partial \theta} \right)^2 + \left( \frac{\partial z}{\partial \theta} \right)^2} = \sqrt{r^2 \cos^2(\theta) \cos^2(\phi) + r^2 \cos^2(\theta) \cos^2(\phi) + r^2 \sin^2(\theta)} = r \\
h_\phi &= \sqrt{\left( \frac{\partial x}{\partial \phi} \right)^2 + \left( \frac{\partial y}{\partial \phi} \right)^2 + \left( \frac{\partial z}{\partial \phi} \right)^2} = \sqrt{r^2 \sin^2(\theta) \sin^2(\phi) + r^2 \sin^2(\theta) \cos^2(\phi)} = r \sin(\theta)
\end{align}
 $$

Et on trouve :

**Le gradient :**
$$
\nabla f=f_{r}\cdot \hat{r}+\frac{1}{r}\,f_{\theta }\cdot \hat{\theta}+ \frac{1}{r\sin \theta}f_{\phi}\hat{\phi}
$$
**La divergence :**
$$\nabla \cdot \mathbf{A} = \frac{1}{r^2} \frac{\partial}{\partial r} (r^2 A_1) + \frac{1}{r \sin \theta} \frac{\partial}{\partial \theta} (\sin \theta A_2) + \frac{1}{r \sin \theta} \frac{\partial A_3}{\partial \phi} $$
**Le Laplacien :**
$$\nabla^2 f = \frac{1}{r^2} \frac{\partial}{\partial r} \left( r^2 f_{r} \right) + \frac{1}{r^2 \sin(\theta)} \frac{\partial}{\partial \theta} \left( \sin(\theta) f_{\theta} \right) + \frac{1}{r^2 \sin^2(\theta)} f_{\phi \phi} $$
## Coordonnées Cylindriques
$$

\left\{
\begin{align}
x&=r\cos(\theta) \\
y&=r\sin(\theta) \\
z&=z
\end{align}
\right.
$$
On trouve :
$$ 
\begin{align}
h_r &= \sqrt{\left( \frac{\partial x}{\partial r} \right)^2 + \left( \frac{\partial y}{\partial r} \right)^2 + \left( \frac{\partial z}{\partial r} \right)^2} = \sqrt{\cos^2(\theta) + \sin^2(\theta)} = 1 \\
h_\theta &= \sqrt{\left( \frac{\partial x}{\partial \theta} \right)^2 + \left( \frac{\partial y}{\partial \theta} \right)^2 + \left( \frac{\partial z}{\partial \theta} \right)^2} = \sqrt{r^2\cos^2(\theta) + r^2\sin^2(\theta)} = r \\
h_z &= \sqrt{\left( \frac{\partial x}{\partial z} \right)^2 + \left( \frac{\partial y}{\partial z} \right)^2 + \left( \frac{\partial z}{\partial z} \right)^2} = \sqrt{1} = 1
\end{align}
 $$

Et on trouve :

**Le gradient :**
$$\nabla f=f_{r}\cdot \hat{r}+\frac{1}{r}\,f_{\theta }\cdot \hat{\theta}+f_{z}\cdot \hat{z}$$
**La divergence :**
$$\frac{1}{r}\, \frac{\partial}{\partial r}(rA_{1})+\frac{1}{r}\, \frac{\partial A_{2}}{\partial \theta}+\frac{\partial A_{3}}{\partial z}$$
**Le Laplacien :**
$$ \nabla^2 f = \frac{1}{r} \frac{\partial}{\partial r} \left( r f_{r} \right) + \frac{1}{r^2} f_{\theta \theta} + f_{zz} $$
**Autres :**
1. L'élement de ligne :
$$\large
dl = dr \, \hat{r} + r \, d\theta \, \hat{\theta} + dz \, \hat{z}
$$
2. L'élement de Volume :
$$\large
dV = r \, dr \, d\theta \, dz
$$
3. L'élément de surface sur une surface de cylindre de rayon constant $\theta$ :
$$\large
dS_{r} = r \, d\theta \, dz
$$
4. L'élément de surface sur une plan d'azimuth constant :
$$\large
dS_{\theta} = dr \, dz
$$
5. L'élément de surface sur une plan d'hauteur constante :
$$
dS_{z}=r\,dr\,d\theta
$$





#### Sources
https://www.jfoadi.me.uk/documents/lecture_mathphys2_05.pdf
Syllabus LEPL1103
https://en.wikipedia.org/wiki/Spherical_coordinate_system
https://en.wikipedia.org/wiki/Cylindrical_coordinate_system