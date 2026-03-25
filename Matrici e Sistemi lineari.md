Siano $m,n\in\mathbb N,\ \ m,n\ne0$.
Una **Matrice** $m$ x $n$ è una tabella con $m$ *righe* e $n$ *colonne* che contiene $m\cdot n$ *oggetti*, detti **coefficienti** della matrice, disposti *ordinatamente*. Una **matrice** con lo stesso numero di *righe* e *colonne*, ossia $m=n$ è detta **matrice quadrata di ordine** $n$.
$$
A=\begin{pmatrix}
 & 1 & 2 & 3  & \\
  & 4 & 5 & 0 & 
\end{pmatrix}
\text{\qquad matrice 2x3 a coefficienti interi}
$$
$$
B=\begin{pmatrix}
 & 1 & i & \\
  & -i & 0 \\
   & 4 & \pi
\end{pmatrix}\text{\qquad matrice 3x2 a coefficienti complessi}
$$

$$
C=\begin{pmatrix}
 & 1 & \sqrt{ 2 } &  \\
  & 0 & -1 & 
\end{pmatrix}\text{\qquad matrice quadrata di ordine 2 a coeff. reali}
$$
*Notazione*:
- $M_{m,n}(S)$ per indicare matrici $m$ x $n$ a coefficienti in $S$
- $M_n(S)$ per indicare l'insieme delle *matrici quadrate* di ordine $n$ a coeff. in $S$

$$
A=\begin{pmatrix}
 & a_{11} & a_{12} & \dots & a_{1n} &  \\
  & a_{21} & a_{22} & \dots & a_{2n} \\
   & \dots & \dots & \dots & \dots \\
    & a_{m1} & a_{m2} & \dots & a_{mn}
\end{pmatrix}=(a_{ij})
$$
$a_{ij}$ è il coefficiente di posto ($i,j$), cioè riga $i$ e colonna $j$.
*Esempio*:  $$A=\begin{pmatrix}
 & -1 & 0 & 1 \\
  & 2 & 3 & 4  & 
\end{pmatrix}\in M_{2,3}(\mathbb Z)$$
$a_{11}=-1\qquad a_{23}=4$ 
*Nota*: le parentesi di una matrice possono essere quadrate, ma *mai* graffe.

*Definizioni*:
1. **Matrice Nulla**: è la matrice in cui tutti i coefficienti sono uguali a 0 $$
\emptyset=\begin{pmatrix}
 & 0 & \dots & 0 &  \\
  & \dots & \dots & \dots \\
   & 0 & \dots & 0
\end{pmatrix}\in M_{m,n}(\mathbb C)
$$
2. **Matrice Identità**: è la matrice quadrata di ordine $n$ che ha tutti 1 nella diagonale principale e 0 nel resto $$
II_{n}=\begin{pmatrix}
 & 1 & 0 & 0 & 0 &  \\
  & 0 & 1 & 0 & 0 \\
   & 0 & 0 & 1 & 0 \\
    & 0 & 0 & 0 & 1
\end{pmatrix}\in M_{n}(\mathbb C)
$$
3. **Vettore Colonna**: è una matrice $m$ x 1 $$
u = \begin{pmatrix}
 & u_{1} &  \\
  & u_{2} \\
   & \dots \\
    & u_{m}
\end{pmatrix}\in M_{m,1}(\mathbb C) = \mathbb C^m
$$
4. **Vettore Riga**: è una matrice 1 x $n$ $$
u = \begin{pmatrix}
 & u_{1} & u_{2} & \dots & u_{n}
\end{pmatrix}\in M_{1,n}(\mathbb C)=\mathbb C_{n}
$$
## Operazioni con le Matrici

### Prodotto Matrice x Scalare
  *Def*: Siano $A=(a_{ij})\in M_{m,n}(\mathbb C)$ una matrice e $\lambda\in\mathbb C$ uno scalare. Il prodotto di $A$ per $\lambda$ è la matrice $$\lambda \cdot A=\left(\lambda \cdot a_{ij}\right)\quad\in M_{m,n}(\mathbb C)$$
*Nota*: il numero $\lambda$ è detto *scalare* perchè riscala uniformemente i coefficienti di $A$.
*Esempio*: $$\begin{align}
 & A=\begin{pmatrix}
 & 1 & -1 &  \\
  & 0 & i \\
   & 2-i & 5
\end{pmatrix}\in M_{3,2}(\mathbb C)
\\ \\
 & \lambda=i\in\mathbb C \\
  & \lambda \cdot A=\begin{pmatrix}
   & i\cdot 1 & i\cdot (-1) &  \\
    & i\cdot 0 & i\cdot i \\
	 & i\cdot (2-i) & i\cdot 5
  \end{pmatrix}=\begin{pmatrix}
   & i & -i &  \\
    & 0 & -1 \\
	 & 1+2i & 5i
  \end{pmatrix}\in M_{3,2}(\mathbb C)
\end{align}$$

#### Proprietà del Prodotto Matrice x Scalare
Siano $A=(a_{ij})\in M_{m,n}(\mathbb C),\ \lambda\in\mathbb C$  Allora:
1. $\lambda \cdot A=\emptyset \Leftrightarrow\lambda=0$ oppure $A=\emptyset$  (perchè in $\mathbb C$ vale la legge di *cancellazione del prodotto* $\lambda\cdot a=0\Leftrightarrow\lambda=0$ oppure $a=0$)
2. Se poniamo $A\cdot\lambda=(a_{ij}\cdot\lambda)$ allora $\lambda\cdot A=A\cdot\lambda$ (perchè il prodotto in $\mathbb C$ è *commutativo*: $\lambda \cdot a=a\cdot\lambda$)
3. Se $\lambda=1$, allora $1\cdot A=A$  (perchè $1$ è l'identità del prodotto in $\mathbb C:\ 1\cdot a=a$)
4. $\lambda \cdot(u\cdot A)=(\lambda \cdot u)\cdot A\quad\forall u\in\mathbb C$.

### Somma di Matrici
Siano $a=(a_{ij}),\ B=(b_{ij})\in M_{m,n}(\mathbb C)$. La **somma di A e B** è la matrice: $$A+B=\left(\ a_{ij}+b_{ij}\ \right)\in M_{m,n}(\mathbb C)$$
*Nota*: la somma è definita **solo se** le due matrici hanno lo stesso numero di righe e lo stesso numero di colonne.

#### Proprietà della Somma
Siano $A,B,C\in M_{m,n}(\mathbb C)$  e  $\lambda,u\in\mathbb C$. Allora:
1. $A+(B+C)=(A+B)+C$  **prop. associativa**
2. $A+B=B+A$  **prop. commutativa**
3. $A+\emptyset=A=\emptyset+A$  **elemento neutro**
4. Indichiamo $-A=(-1)\cdot A$  allora  $A + (-A)=\emptyset$  ($-A$ è **matrice opposta** di $A$)
5. $\lambda \cdot(A+B)=\lambda \cdot A+\lambda \cdot B$  **prop. distributiva**
6. $(\lambda+u)\cdot A=\lambda \cdot A+u\cdot A$  **prop. distributiva**

### Prodotto Riga x Colonna
*Def*: Siano $u=(u_{1},\dots,u_{n})\in\mathbb C_{n}$ un *vettore riga*  e  $v=\begin{pmatrix} & v_{1} &  \\  & \dots \\  & v_{n}\end{pmatrix}\in\mathbb C^n$ un *vettore colonna*.
Il prodotto $u\cdot v$ è: $$u\cdot v=(u_{1},\dots,u_{n})\cdot$$