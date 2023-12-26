Dans le cours on va s'intéresser aux EDPs ***quasi-linéaires***.
$$
\large P(x,y) \frac{\partial u(x,y)}{\partial x}+Q(x,y)\frac{\partial u(x,y)}{\partial y}=R(x,y,u)
$$
L'idée est que si le problème en question est ***bien posé***, on pourra le résoudre en utilisant les ***équations de compatibilité***. 
$$
\large P\, \text{d}u=R\,\text{d}x \quad\ \Leftrightarrow \quad\ Q\, \text{d}u=R\, \text{d}y
$$
On sait aussi que le problème est bien posé si les ***courbes caractéristiques*** définies par :
$$
\large Pdx=Qdy
$$
ne se croisent jamais et n'ont qu'une intersection avec la condition initiale/condition limite.

On peut construire les courbes caractéristiques en intégrant à partir de la condition initiale mais on peut également calculer $\large \frac{dy}{dx}$ et ainsi tracer la courbe approximativement à la main.

L'équation des courbes caractéristiques nous permet également de comprendre l'équivalence entre les deux équations de compatibilité.


### Systèmes d'EDP du Premier Ordre
On peut généraliser les EDP du premier ordre à des systèmes d'EDP. Considérons le système quasi-linéaire suivant :
$$\large
M_1 \frac{\partial u}{\partial x} + N_1 \frac{\partial u}{\partial y} + P_1 \frac{\partial v}{\partial x} + Q_1 \frac{\partial v}{\partial y} = R_1,
$$
$$\large
M_2 \frac{\partial u}{\partial x} + N_2 \frac{\partial u}{\partial y} + P_2 \frac{\partial v}{\partial x} + Q_2 \frac{\partial v}{\partial y} = R_2,
$$

Où les coefficients sont au maximum, fonctions de $\large x,y,u,v$. Pour le problème de Cauchy, les valeurs $\large u(s)$ et $\large v(s)$ sont données le long de la courbe $\large \Gamma$, $\large u_{s}$ et $\large v_{s}$ sont donc aussi connu.

$$\large
\frac{\partial u}{\partial x}\frac{dx}{ds} + \frac{\partial u}{\partial y}\frac{dy}{ds} = \frac{du}{ds}
$$
$$\large
\frac{\partial v}{\partial x}\frac{dx}{ds} + \frac{\partial v}{\partial y}\frac{dy}{ds} = \frac{dv}{ds}
$$
Ce qui donne le système :
$$ \large\begin{pmatrix} M_1 & N_1 & P_1 & Q_1 \\ M_2 & N_2 & P_2 & Q_2 \\ \frac{dx}{ds} & \frac{dy}{ds} & 0 & 0 \\ 0 & 0 & \frac{dx}{ds} & \frac{dy}{ds} \end{pmatrix} \begin{pmatrix} \frac{\partial u}{\partial x} \\ \frac{\partial u}{\partial y} \\ \frac{\partial v}{\partial x} \\ \frac{\partial v}{\partial y} \end{pmatrix} = \begin{pmatrix} R_1 \\ R_2 \\ \frac{du}{ds} \\ \frac{dv}{ds} \end{pmatrix} $$
Tant que le déterminant ne s'annule pas, on peut le résoudre pour obtenir $\large u_{x},u_{y},v_{x},v_{y}$ le long de $\large \Gamma$ et donc construire la solution en dehors de $\large \Gamma$. On définit des directions caractéristiques ($\large dx,dy$) par le déterminant :
$$
\large \begin{vmatrix} M_1 & N_1 & P_1 & Q_1 \\ M_2 & N_2 & P_2 & Q_2 \\ dx & dy & 0 & 0 \\ 0 & 0 & dx & dy \end{vmatrix}=0
$$
Ces directions sont alors obtenues comme les racines de :
$$\large
A (dy)^2 - B dy dx + C (dx)^2 = 0,
$$
Où les coefficients $\large A,B,C$ sont définis comme suit :
$$\large
A = M_1 P_2 - M_2 P_1,
$$
$$\large
B = (P_2 N_1 - P_1 N_2) + (Q_2 M_1 - Q_1 M_2)
$$
$$\large
C = N_1 Q_2 - N_2 Q_1
$$
Le signe de $\large B^{2}-4AC$ détermine encore une fois, le type de problème (hyperbolique, ...) et la nature des solutions (réelles, confondues, imaginaires). Dans le cas hyperbolique et comme vu précédemment avec les caractéristiques de deuxième ordre, on peut utiliser la règle de Cramer pour trouver les relations de compatibilité par exemple en remplaçant la troisième colonne :
$$
\large \begin{vmatrix} M_1 & N_1 & R_1 & Q_1 \\ M_2 & N_2 & R_2 & Q_2 \\ dx & dy & du & 0 \\ 0 & 0 & dv & dy \end{vmatrix}=0
$$
