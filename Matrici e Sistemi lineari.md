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
*Esempio*: $$
A=\begin{pmatrix}
 & -1 & 0 & 1 \\
  & 2 & 3 & 4  & 
\end{pmatrix}\in M_{2,3}(\mathbb Z)
$$
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
1. **Prodotto Matrice x Scalare**:  *Def*: Siano $A=(a_{ij})\in M_{m,n}(\mathbb C)$ una matrice e $\lambda\in\mathbb C$ uno scalare. Il prodotto di $A$ per $\lambda$ è la matrice $$
\lambda \cdot A=\left(\lambda \cdot a_{ij}\right)\quad\in M_{m,n}(\mathbb C)
$$