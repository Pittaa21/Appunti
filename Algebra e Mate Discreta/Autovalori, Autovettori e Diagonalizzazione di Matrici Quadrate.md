## Autovalori e Autovettori
*Def*: Sia $A\in M_{n}(\mathbb K)$ una matrice quadrata, $\mathbb K\in \{ \mathbb R,\mathbb C \}$. Un ***autovalore*** di $A$ è uno scalare $\lambda\in\mathbb C$ per cui esiste un vettore non-nullo $\underline{0}\neq \underline{v}\in\mathbb K^n$ tale che: $$A\cdot \underline{v}=\lambda \cdot \underline{v}$$L'==insieme di tutti gli autovalori== di $A$ si chiama ***spettro*** di $A$, e si indica con $\text{Spec}(A)$.
Un vettore $\underline{v}\in\mathbb K^n$ tale che$$A\cdot \underline{v}=\lambda \cdot \underline{v}$$per un qualche $\lambda\in\mathbb C$, è detto ***autovettore*** di $A$ (relativo all'**autovalore** $\lambda$).

*Esempio*: $$A=\begin{pmatrix}
2 & 1 \\
0 & 1
\end{pmatrix}\in M_{2}(\mathbb R)$$ $A\cdot \begin{pmatrix}1 \\ 0\end{pmatrix}=2\cdot \begin{pmatrix}1 \\ 0\end{pmatrix}$ quindi $2$ è **autovalore** di $A$ e $\begin{pmatrix}1 \\ 0\end{pmatrix}$ è **autovettore** di $A$ (relativo a $2$)

*Osservazioni*:
1. $\forall \lambda\in\mathbb C,\ \forall A\in M_{n}(\mathbb K)$ si ha $$A\cdot \underline{0}=\underline{0}=\lambda \cdot \underline{0}$$cioè $\underline{0}$ è **autovettore** di $A$ per ogni $\lambda$
2. Se $\underline{v}\in\mathbb K^n$ è un **autovettore** di $A\in M_{n}(\mathbb K)$ allora lo è rispetto ad un ==unico== **autovalore**.
3. Se $\lambda\in\mathbb C$ è un **autovalore** di $A\in M_{n}(\mathbb K)$, allora esistono ==infiniti== **autovettori** di $A$ relativi a $\lambda$.

*Notazione*: Indichiamo con $E_{A}(\lambda)$ l'***insieme degli autovettori*** di $A$ relativi all'**autovalore** $\lambda$:$$E_{A}(\lambda)=\{ \underline{v}\in\mathbb K^n\ |\ A\cdot \underline{v}=\lambda \cdot \underline{v} \}\subseteq\mathbb K^n$$
###### Proprietà di $E_{A}(\lambda)$
1. $\underline{0}\in E_{A}(\lambda)$
2. Se $E_{A}(\lambda)=\{ \underline{0} \}$ allora ==non esistono== vettori non-nulli $\underline{v}\in\mathbb K^n$ tali che $A\cdot \underline{v}=\lambda \cdot \underline{v}$, cioè $\lambda$ ==non== è **autovalore** di $A$.$$\lambda\text{ è autovalore di }A\Leftrightarrow E_{A}(\lambda)\neq \{ \underline{0} \}$$
3. $E_{A}(\lambda)=N(A-\lambda \cdot\mathbb 1_{n})$ spazio nullo della matrice $A-\lambda \cdot\mathbb 1_{n}$.
    $E_{A}(\lambda)$ è uno sottospazio vettoriale di $\mathbb K^n$ chiamato ***autospazio*** di $A$ relativo a $\lambda$.

$\text{dim }(E_{A}(\lambda))=n-rk(A-\lambda \cdot \mathbb1_{n})$ è detta ***molteplicità geometrica*** di $\lambda$, indicata $d_{A}(\lambda)$.

#### Polinomio caratteristico
$$\lambda\text{ è autovalore di }A\Leftrightarrow\det(A-\lambda \cdot\mathbb 1_{n})=0$$cioè gli **autovalori** di $A$ sono ==tutti gli zeri del polinomio==:$$P_{A}(x)=\det(A-x\cdot\mathbb 1_{n})$$detto ***polinomio caratteristico*** di $A$.

##### Proprietà Polinomio caratteristico
Sia $A\in M_{n}(\mathbb K)$. Allora:
1. $\text{deg}(P_{A}(x))=n$
2. in $P_{A}(x)$ il coefficiente di $x^n$ è $(-1)^n$
3. Il **Teorema Fondamentale dell'Algebra** ci dice che:$$P_{A}(x)=(-1)^n\cdot(x-z_{1})\cdot(x-z_{2})\dots(x-z_{n})$$dove $z_{i}$ sono gli ***zeri complessi*** di $P_{A}(x)$, cioè gli **autovalori** di $A$.<br><br>Raggruppando gli **autovalori** ripetuti, otteniamo:$$P_{A}(x)=(-1)^n\cdot(x-\lambda_{1})^{m_{1}}\dots (x-\lambda_{t})^{m_{t}}$$Il numero $m_{i}=m_{A}(\lambda_{i})$ è detto ***molteplicità algebrica*** dell'**autovalore** $\lambda_{i}$.

##### Teorema
Sia $A\in M_{n}(\mathbb K)$ e $\lambda\in \text{Spec}(A)$. Allora:$$1\leq d(\lambda)\leq m(\lambda)$$Se $m(\lambda)=1$ (**molteplicità algebrica**) allora $d(\lambda)=1$ (**molteplicità geometrica**).

## Matrici Simili e Diagonalizzabili
*Def*: Due matrici quadrate $A,B\in M_{n}(\mathbb K)$ si dicono ***simili*** se esiste una matrice quadrata $S\in M_{n}(\mathbb K)$ **non singolare** (*invertibile*) tale che:$$A=S\cdot B\cdot S^{-1}$$
*Osservazione*: Se $A=S\cdot B\cdot S^{-1}$ allora ponendo $T=S^{-1}$ si ha $B=T\cdot A\cdot T^{-1}$, dunque $A$ è simile a $B$ se e solo se $B$ è simile ad $A$.

##### Teorema
Se $A,B\in M_{n}(\mathbb K)$ sono **simili**, allora:
1. $P_{A}(x)=P_{B}(x)$
2. $\forall \lambda\in \text{Spec}(A),\quad \text{dim}(E_{A}(\lambda))=\text{dim}(E_{B}(\lambda))$

*Def*: Una matrice quadrata $A\in M_{n}(\mathbb K)$ si dice ***Diagonalizzabile*** se è simile ad una matrice diagonale, cioè se esistono:
- una matrice **diagonale** $D=\begin{pmatrix}d_{1} &  &  \\  & \dots \\  &  & d_{n}\end{pmatrix}\in M_{n}(\mathbb K)$
- una matrice **non singolare** $S\in M_{n}(\mathbb K)$ tali che $$A=S\cdot D\cdot S^{-1}$$
*Nota*: se $A$ è **diagonalizzabile**, tali $S$ e $D$ sono chiamate una "diagonalizzazione di $A$".

*Osservazione*: Ogni matrice diagonale è diagonalizzabile: basta prendere $S=\mathbb 1_{n}=S^{-1}\quad D=\mathbb 1_{n}\cdot D\cdot\mathbb 1_{n}$

*Applicazione*: Sapere che una matrice $A$ è diagonalizzabile è utile, ad esempio, per calcolare le potenze di $A$.

$A\cdot A=A^2=(S\cdot D\cdot S^{-1})\cdot(S\cdot D\cdot S^{-1})=$
$=S\cdot D\cdot (S^{-1}\cdot S)\cdot D\cdot S^{-1}=S\cdot D^2\cdot S^{-1}=$

$=S\cdot \begin{pmatrix}d_{1}^2 &  &  \\  & \dots &  \\  &  & d_{n}^2\end{pmatrix}\cdot S^{-1}$

##### Teorema (caratterizzazione delle matrici diagonalizzabili)
Sia $A\in M_{n}(\mathbb K)$ una matrice quadrata.
Siano:
- $\lambda_{1},\dots,\lambda_{t}$ gli autovalori di $A$
- $m(\lambda_i)$ la **molt. algebrica** di $\lambda_{i}$
- $d(\lambda_{i})$ la **molt. geometrica** di $\lambda_{i}$
Allora:$$A\text{ è diagonalizzabile }\ \Leftrightarrow\ \ m(\lambda_{i})=d(\lambda_{i})\quad\forall i=1,\dots,t$$cioè se per ogni *autovalore* di $A$ le **molteplicità algebrica** e **geometrica** coincidono.

*Osservazioni*:
1. Se tutti gli *autovalori* di $A$ hanno **molteplicità algebrica** uguale a 1 ($P_{A}(x)=(x-\lambda_{1})\cdot\dots(x-\lambda_{t})$) con $\lambda_{i}\neq \lambda_{j}\quad\forall i\neq j$. Allora $A$ è ***diagonalizzabile***, perchè $\forall i,1\leq d(\lambda_{i})\leq m(\lambda i)=1\implies d(\lambda_{i})=m(\lambda_{i})=1$.<br>
2. Il viceversa è falso, cioè esistono matrici ***diagonalizzabili*** in cui almeno un *autovalore* ha **molteplicità algebrica** maggiore di 1.

*Osservazione*: Le operazioni elementari sulle righe di una matrice ==non== preservano *autovalori* e *autovettori*.

## Matrici Unitariamente Diagonalizzabili
*Def*: Una matrice quadrata $U\in M_{n}(\mathbb K)$ invertibile si dice:
- ***Unitaria*** se $U^{-1}=U^H$ (cioè $U\cdot U^H=\mathbb 1_{n}=U^H\cdot U$)
- ***Togonale*** se $U^{-1}=U^T$ (cioè $U\cdot U^T=\mathbb 1_{n}=U^T\cdot U$)

*Osservazione*:
- se $U\in M_{n}(\mathbb R)$ allora $U^H=U^T$, quindi ogni matrice **unitaria** è anche **ortogonale**.
- se $U\in M_{n}(\mathbb C)$, non è sempre vero

*Def*: Una matrice quadrata $A\in M_{n}(\mathbb K)$ si dice ***unitariamente diagonalizzabile*** se è simile ad una matrice diagonale $D$ tramite una matrice unitaria $U$:$$A=U\cdot D\cdot U^{-1}=U\cdot D\cdot U^H$$
*Osservazione*: se $A$ è unitariam. diag., allora $A$ è **diagonalizzabile**. Il viceversa è generalmente falso.

#### Teorema Spettrale (moltiplicativo)
Sia $A\in M_{n}(\mathbb K)$. 
$A$ è **unitariamente diagonalizzabile** $\Leftrightarrow\ A\cdot A^H=A^H\cdot A$ ($A$ è una matrice **normale**)

###### Esempi matrici normali
(quindi unit. diag.)
1. Matrici **diagonali**:$$A=\begin{pmatrix}
a_{1} &  &  \\
 & \dots &  \\
  &  & a_{n}
\end{pmatrix}$$
2. Matrici **unitarie**: $U\cdot U^H=\mathbb 1_{n}=U^H\cdot U$
3. Matrici **hermitiane**: $A=A^H\implies A\cdot A^H=A^2=A^H\cdot A$
4. Matrici **anti-hermitiane**: $A=-A^H\implies A\cdot A^H=A\cdot(-A)=-A^2=A^H\cdot A$

##### Costruzione diagonalizzazione unitaria
Sia $A\in M_{n}(\mathbb K)$ **unitariamente diagonalizzabile**. Vogliamo trovare una matrice diagonale $D\in M_{n}(\mathbb K)$ e una matrice unitaria $U\in M_{n}(\mathbb K)$ tali che $$A=U\cdot D\cdot U^H$$
$A$ è simile a $D$, dunque 