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
Il prodotto $u\cdot v$ è: $$u\cdot v=(u_{1},\dots,u_{n})\cdot \begin{pmatrix}
 & v_{1} &  \\
  & \dots \\
   & v_{n}
\end{pmatrix}=\sum_{i=1}^n u_{i}\cdot v_{i}=u_{1}\cdot v_{1}+u_{2}\cdot v_{2}+\dots+u_{n}\cdot v_{n}\in\mathbb C$$
*Nota*: il risultato di $u\cdot v$ è **un numero** per questo il prodotto descritto sopra è anche chiamato **prodotto scalare di vettori**.
*Esempio*: $u=\begin{pmatrix} & 7 & -1 & i & \end{pmatrix}\in\mathbb C_{3},\ v=\begin{pmatrix} & -1 &  \\  & 2i \\  & 0\end{pmatrix}\in\mathbb C^3$.  
$u\cdot v=7\cdot(-1)+(-1)\cdot 2i+i\cdot 0=-7-2i\in\mathbb C$

*Osservazioni*:
1. $\begin{pmatrix} & u_{1} & \dots & u_{n} & \end{pmatrix}\cdot \begin{pmatrix} & v_{1} &  \\  & ...  \\ & v_{n}\end{pmatrix} = \begin{pmatrix} & v_{1} & \dots & v_{n}\end{pmatrix}\cdot \begin{pmatrix} & u_{1} &  \\  & \dots \\  & u_{n}\end{pmatrix}$
2. Non vale la *legge di cancellazione* del prodotto, cioè se $u\cdot v=0$ non è detto che $u=\begin{pmatrix} & 0 & \dots & 0 & \end{pmatrix}$ oppure $v=\begin{pmatrix} & 0 &  \\  & \dots \\  & 0\end{pmatrix}$

*Definizione*: Siano $A\in M_{m,r}(\mathbb C)\qquad B\in M_{r,n}(\mathbb C)$ 
Il **prodotto riga x colonna di A e B** è la matrice: $A\cdot B\in M_{m,n}(\mathbb C)$  dove l'elemento di posto ($i,j$) in $A\cdot B$ è dato da: ( riga $i$-esima di $A$ ) $\cdot$ ( colonna $j$-esima di $B$ )

*Nota*: si può calcolare $A\cdot B$ solo se il *numero di colonne di A* = *numero di righe di B*
*Esempio*:$$\begin{align}
 & A=\begin{pmatrix}
 & 3 & 1 & -i &  \\
  & 0 & i & 2
\end{pmatrix}\in M_{2,3}(\mathbb C)\qquad B=\begin{pmatrix}
 & 2i & 4 & 1 &  \\
  & -1 & 0 & 2 \\
   & 1 & -i & i
\end{pmatrix}\in M_{3}(\mathbb C) \\
 & A\cdot B=\begin{pmatrix}
  & c_{ij} & 
 \end{pmatrix}\qquad\text{dove} \\
  & c_{11}=\begin{pmatrix}
  & 3 & 1 & -i & 
 \end{pmatrix}\cdot \begin{pmatrix}
  & 2 &  \\
   & -1 \\
    & 1
 \end{pmatrix}=3\cdot 2+1\cdot(-i)+(-i)\cdot 1=5-i \\
  & c_{12}=\begin{pmatrix}
   & 3 & 1 & -i & 
  \end{pmatrix}\cdot \begin{pmatrix}
   & 4 &  \\
    & 0 \\
    & -i
  \end{pmatrix}=3\cdot 4+1\cdot 0+(-i)\cdot(-i)=11 \\
   & \dots \\
   & A\cdot B=\begin{pmatrix}
    & c_{11} & c_{12} & c_{13} &  \\
	 & c_{21} & c_{22} & c_{23}
   \end{pmatrix}=\begin{pmatrix}
    & -1+5i & 11 & 6 &  \\
	 & 2-i & -2i & 4i
   \end{pmatrix}\in M_{2,3}(\mathbb C)\end{align}$$
### Proprietà del Prodotto Riga x Colonna
Siano $A,B,C$ matrici a coefficienti complessi per cui le operazioni descritte di seguito sono definite e sia $\alpha\in\mathbb C$. Allora:
1. $A\cdot(B\cdot C)=(A\cdot B)\cdot C$  **propr. associativa**
2. $A\cdot \emptyset=\emptyset=\emptyset \cdot A$
3. $A\cdot \mathbb 1_{n}=A=\mathbb 1_{m}\cdot A\qquad A\in M_{m,n}(\mathbb C)$
4. $A\cdot(B+C)=A\cdot B+A\cdot C$
5. $(A+B)\cdot C=A\cdot C+B\cdot C$
6. $\alpha \cdot(A\cdot B)=(\alpha \cdot A)\cdot B=A\cdot(\alpha \cdot B)$

*Nota*: 
- Il prodotto riga x colonna **NON** gode della **proprietà commutativa** ( $A\cdot B\ne B\cdot A$ ).
- Il prodotto riga x colonna **NON** gode della **proprietà di cancellazione del prodotto**

## Sistemi Lineari
*Definizione*: Un **sistema lineare** (a coefficienti complessi) di $m$ *equazioni* in $n$ *incognite*, $m,n\in\mathbb N,\ m\ne0\ne n$ è un insieme di $m$ *equazioni* di 1° grado nelle stesse $n$ *incognite* $x_{1},x_{2},\dots,x_{n}$.$$\begin{cases}
a_{11}\cdot x_{1}+a_{12}\cdot x_{2}+\dots+a_{1n}\cdot x_{n}=b_{1} \\
a_{21}\cdot x_{1}+a_{22}\cdot x_{2}+\dots+a_{2n}\cdot x_{n}=b_{2} \\
\dots \\
a_{m1}\cdot x_{1}+a_{m2}\cdot x_{2}+\dots+a_{mn}\cdot x_{n}=b_{m}
\end{cases}$$
Dato un **sistema lineare** di $m$ *equazioni* in $n$ *incognite*, chiamiamo
- **matrice (incompleta) dei coefficienti**: la matrice $A=(a_{ij})\in M_{m,n}(\mathbb C)$
- **vettore dei termini noti**: il vettore $$b=\begin{pmatrix}b_{1} \\ \dots \\ b_{m}\end{pmatrix}\in\mathbb C^m$$
- **vettore delle incognite**: il vettore $$x=\begin{pmatrix}x_{1} \\ x_{2} \\ \dots \\ x_{n}\end{pmatrix}\in\mathbb C^n$$

Il sistema lineare può essere riscritto come$$A\cdot x=b$$
Risolvere un *sistema lineare* di $m$ equazioni in $n$ incognite corrispondente a $A\cdot x=b$ significa determinare il sottoinsieme di $\mathbb C^n$ $$\left\{z=\begin{pmatrix}
z_{1} \\
\dots \\
z_{n}
\end{pmatrix}\in\mathbb C^n:\ A\cdot z=b\right\}$$detto **insieme delle SOLUZIONI del SISTEMA**.
*Nota*: Può capitare che
- le soluzioni *non esistano* oppure
- le soluzioni siano *infinite* oppure
- ci sia un'*unica soluzione*

*Definizione*: Dato un **sistema lineare** $A\cdot x=b$, con $A=(a_{ij})\in M_{m,n}(\mathbb C)$ e $b=\begin{pmatrix}b_{1} \\ \dots \\ b_{m}\end{pmatrix}\in\mathbb C^m$  la **matrice completa** (*aumentata*) del sistema è la matrice:$$\left(\ A|B\ \right)=\begin{pmatrix}
 & a_{11} & a_{12} & \dots & a_{1n} & | & b_{1} \\
  & \dots  & \dots & \dots & \dots & | & \dots \\
   & a_{m1} & \dots & \dots & a_{mn} & | & b_{m} & 
\end{pmatrix}\in M_{m,n+1}(\mathbb C)$$
### Algoritmo di Eliminazione di Gauss
