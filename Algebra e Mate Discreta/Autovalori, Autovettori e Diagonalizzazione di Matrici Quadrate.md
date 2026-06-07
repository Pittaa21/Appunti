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