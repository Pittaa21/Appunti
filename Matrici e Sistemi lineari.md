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

*Esempio*: $A=\begin{pmatrix}1 & 2 & -i \\ 0 & 4i & 1\end{pmatrix}\quad B=\begin{pmatrix}3 & -i & 1 \\ 3 & 2 & i\end{pmatrix}$
$$A+B=\begin{pmatrix}
1+3 & 2+(-i) & -i+1 \\
0+3 & 4i+2 & 1+i
\end{pmatrix}=\begin{pmatrix}
4 & 2-i & 1-i \\
3 & 2+4i & 1+i
\end{pmatrix}$$
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
## Algoritmo di Eliminazione di Gauss
L'**Algoritmo di Eliminazione di Gauss** permette di risolvere il *sistema lineare* $A\cdot x=b$ operando opportune **operazioni sulle righe** di ($A|b$) in modo da ottenere una **matrice a gradini** ($C|d$), detta **forma ridotta (di Gauss)** di $A$ che corrisponde al *sistema lineare*:$$C\cdot x=d$$(più facile da risolvere)

#### Operazioni elementari su righe di matrice
1. **Scambio di righe**  *Esempio*: $E_{ij}$ (scambio le righe $i$ e $j$) $$\begin{pmatrix}
 & 0 & i & 2 & -3 &  \\
  & 1 & 2i & 0 & -1 \\
   & 1 & 2i & 1 & 0
\end{pmatrix}\quad\rightarrow E_{12}\rightarrow\quad \begin{pmatrix}
 & 1 & 2i & 0 & -1 &  \\
  & 0 & i & 2 & -3 \\
   & 1 & 2i & 1 & 0
\end{pmatrix}$$*Nota* è come scabiere 2 equzioni del sistema
2. **Moltiplicazione della riga $i$ x scalare** $\alpha \in\mathbb C,\ \alpha\ne0\quad E_{i}(\alpha)$ *Esempio*:$$\begin{pmatrix}
 & 1 & 2i & 0 & -1 &  \\
  & 0 & i & 2 & -3 \\
   & 1 & 2i & 1 & 0
\end{pmatrix}\quad\rightarrow E_{2}(-i)\rightarrow\quad\begin{pmatrix}
 & 1 & 2i & 0 & -1 &  \\
  & 0 & 1 & -2i & 3i \\
  1 & 2i & 1 & 0
\end{pmatrix}$$*Nota*: è come moltiplicare per $\alpha$ tutti i **coefficienti** di un'equazione e anche il **termine noto**.
3. **Somma della riga $i$ con un multiplo scalare** $\alpha\in\mathbb C,\ \alpha\ne 0$ **della riga $j$**   $E_{ij}(\alpha)$ *Esempio*:$$\begin{pmatrix}
 & 1 & 2i & 0 & -1 &  \\
  & 0 & 1 & -2i & 3i \\
   & 1 & 2i & 1 & 0
\end{pmatrix}\quad\rightarrow E_{31}(-1)\rightarrow\quad\begin{pmatrix}
 & 1 & 2i & 0 & -1 &  \\
  & 0 & 1 & -2i & 3i \\
   & 0 & 0 & 1 & 1
\end{pmatrix}$$*Nota*: corrisponde a sostituire l'$i$-esima equazione del sistema con la somma della stessa con $\alpha$ volte la $j$-esima equazione.

*Osservazione*: Se si applicano le **regole elementari** sulle righe della matrice **completa** $A|b$ si ottiene una matrice $C|d$ che corrisponde al sistema $C\cdot x=d$ che ha le *stesse soluzioni* di $A\cdot x=b$.

### Matrici a Gradini
*Definizione*: Una **matrice a gradini** (o **scala**) è una matrice della forma:$$\begin{pmatrix}
 & 0 & \dots & 0 & 1 & \dots & \dots & \dots & \dots &  \\
  & 0 & \dots & \dots & 0 & 1 & \dots & \dots & \dots \\
   & \dots & \dots & \dots & \dots & 0 & 1 & \dots & \dots \\
    & 0 & \dots & \dots & \dots & \dots & 0 & 1 & \dots \\
	 & 0 & \dots & \dots & \dots & \dots & \dots &  \dots & 0
\end{pmatrix}$$dove
1. Tutte le righe nulle sono in fondo alla matrice
2. Nelle righe non nulle, il primo coefficiente diverso da **zero** e uguale a 1 ed è chiamato *Pivot*
3. Per ogni *Pivot* di posto ($i,j$), il *pivot* della riga successiva si trova nel posto ($i+1,j+k$) con $k>0$ (quindi più a destra del *pivot* precedente)

*Definizione*: Le colonne di una matrice a gradini contenenti un *pivot* sono dette **dominanti**, le altre sono **libere**.

*Esempio*: Risolvere il sistema lineare$$\begin{cases}
 x_{1}-x_{2}+2x_{3}=0 \\
 2x_{1}-2x_{2}+x_{3}=4
\end{cases}$$con il metodo di **Eliminazione di Gauss**.
La *matrice completa* è:$$\begin{align}
 & A|b=\begin{pmatrix}
  & 1 & -1 & 2 & | & 0 &  \\
   & 2 & -2 & 1 & | & 4
 \end{pmatrix} \\
  & E_{21}(-2)\rightarrow \begin{pmatrix}
   & 1 & -1 & 2 & | & 0 \\
    & 0 & 0 & -3 & | & 4
  \end{pmatrix} \\
   & E_{2}\left( -\frac{1}{3} \right)\rightarrow\begin{pmatrix}
    & 1 & -1 & 2 & | & 0 &  \\
	 & 0 & 0 & 1 & | & -\frac{4}{3}
   \end{pmatrix}=(C|d)
\end{align}$$
$C\cdot x=d$ è il *sistema lineare*$$\begin{align}
&\begin{cases}
x_{1}-x_{2}+2x_{3}=0 \\
x_{3}=-\frac{4}{3}
\end{cases} \\
&\Rightarrow \begin{cases}
x_{1}-x_{2}+2\cdot\left( -\frac{4}{3} \right)=0 \\
x_{3}=-\frac{4}{3}
\end{cases} \\
&\Rightarrow \begin{cases}
x_{1}-x_{2}=\frac{8}{3} \\
x_{3}=-\frac{4}{3}
\end{cases}
\end{align}$$*Osservazioni*:
- la colonna $d$ (**termine noto**) è *libera*, dunque il sistema ammette soluzioni
- la seconda colonna è *libera*, quindi all'incognita $x_{2}$ posso associare un parametro $z$$$\begin{cases}
x_{1}-x_{2}=\frac{8}{3} \\
x_{2}=z \\
x_{3}=-\frac{4}{3}
\end{cases}\Rightarrow \begin{cases}
x_{1}=z+\frac{8}{3} \\
x_{2}=z \\
x_{3}=-\frac{4}{3}
\end{cases}$$L'insieme delle soluzioni è:$$\left\{\begin{pmatrix}
 & z+\frac{8}{3} &  \\
  & z \\
   & -\frac{4}{3}
\end{pmatrix}:\ z\in\mathbb C\right\}$$(le soluzioni sono infinite e dipendono da 1 parametro)
*Esempio*: 
$z=0\rightarrow \begin{pmatrix} & \frac{8}{3} &  \\  & 0 \\  & -\frac{4}{3}\end{pmatrix}$ è una soluzione

$z=-\frac{8}{3}\rightarrow \begin{pmatrix} & 0 &  \\  & -\frac{8}{3} \\  & -\frac{4}{3}\end{pmatrix}$ è una soluzione


Consideriamo il sistema lineare $A\cdot x =b$ e una **forma ridotta di Gauss** $(C|d)$ della matrice completa $(A|b)$.
*Osservazione*: Stabilire quali colonne di ( $C|d$ ) sono **libere** e quali sono **dominanti** ci da informazioni sulle soluzioni del sistema.

**Caso 1**: $d$ è colonna dominante$$(C|d)=\begin{pmatrix}
 & 0 & \dots & 0 & 1 & \dots & | & \dots &  \\
  & 0 & \dots & \dots & 0 & 1 & | & \dots  \\
   & 0 & \dots & \dots & \dots & 0 & | & 1 \\
    & 0 & \dots & \dots & \dots & \dots & | & 0
\end{pmatrix}$$ il sistema allora *non ha soluzioni* (l'ultima equazione è 0 = 1).

**Caso 2**: $d$ non è dominante e tutte le colonne di $C$ sono dominanti$$(C|d)=\begin{pmatrix}
 & 1 & \dots & \dots & | & d_{1} &  \\
  & 0 & 1 & \dots & | & d_{2} \\
   & \dots & 0 & 1 & | & d_{n} \\
    & 0 & \dots & 0 & | & 0
\end{pmatrix}$$ il sistema allora ha *una soluzione*.

**Caso 3**: $d$ non è dominante e in $C$ ci sono $k\ge1$ colonne libere.$$A=\begin{pmatrix}
 & 1 & 3 & -2 & 1 &  \\
  & 0 & 0 & 2 & 4 \\
   & 2 & 6 & -3 & 4
\end{pmatrix}\quad b=\begin{pmatrix}
 & -1 &  \\
  & 2 \\
   & -1
\end{pmatrix}$$ il sistema ha *infinite soluzioni* dipendenti da $K$ parametri ($\infty^K$ soluzioni).

### Sistema lineare dipendente dal parametro $\alpha$
Risolvere il sistema dipendente dal parametro $\alpha\in\mathbb C$


### Rango di una matrice
*Definizione*: Il **rango** di una matrice $A\in M_{m.n}(\mathbb C)$ è il **numero di colonne dominanti** di una forma ridotta di $A$. Lo indichiamo con $rk(A)$.

*Esempio*: Se $A\in M_{3}(\mathbb C),\ A\ne0$ e $C$ è una sua forma ridotta allora ci sono le possibilità:
- $rk(A)=3$, tutte le colonne di $C$ sono *dominanti*$$C=\begin{pmatrix}
 & 1 & a & b &  \\
  & 0 & 1 & c \\
   & 0 & 0 & 1
\end{pmatrix}$$
- $rk(A)=2$, 2 colonne di $C$ sono *dominanti*$$C=\begin{pmatrix}
 & 1 & a & b &  \\
  & 0 & 1 & c \\
   & 0 & 0 & 0
\end{pmatrix},\quad\begin{pmatrix}
 & 1 & a & b &  \\
  & 0 & 0 & 1 \\
   & 0 & 0 & 0
\end{pmatrix},\quad\begin{pmatrix}
 & 0 & 1 & a &  \\
  & 0 & 0 & 1  \\
   & 0 & 0 & 0
\end{pmatrix}$$
- $rk(A)=1$, 1 colonna di $C$ è *dominante*$$C=\begin{pmatrix}
 & 1 & a & b &  \\
  & 0 & 0 & 0  \\
   & 0 & 0 & 0
\end{pmatrix},\quad\begin{pmatrix}
 & 0 & 1 & a &  \\
  & 0 & 0 & 0  \\
   & 0 & 0 & 0
\end{pmatrix},\quad\begin{pmatrix}
 & 0 & 0 & 1 &  \\
  & 0 & 0 & 0 \\
   & 0 & 0 & 0
\end{pmatrix}$$

*Osservazioni*: sia $A\in M_{m,n}(\mathbb C),\ A\ne \emptyset$ e sia $C$ una sua forma ridotta
1. $1\le rk(A)\le n$
2. il sistema $A\cdot x=b$ ha un'unica soluzioni $\Leftrightarrow$ tutte le colonne di $C$ sono dominanti $\Leftrightarrow\ rk(A)=n$ $\ \ \ n$ è il numero di incognite ($x_{1},\dots,x_{n}$)
3. $rk(A)=$ numero di gradini di $C$ $=$ numero di righe *non-nulle* di $C$ $\le m$ (numero totale di righe). Cioè il rango di $A$ è sempre minore o uguale al numero di righe di $A$. Questo implica che se $m<n$ (il numero di equazioni è minore del numero di incognite) allora $rk(A)\le m<n$ e il sistema **non** può avere un'*unica soluzione* ( o è impossibile o ne ha infinite).

## Matrici Invertibili
*Definizione*: una matrice quadrata $A\in M_{n}(\mathbb C)$ si dice **invertibile** (o *non singolare*) se esiste una matrice quadrata $B\in M_{n}(\mathbb C)$ tale che $$A\cdot B=\mathbb 1_{n}=B\cdot A$$
*Osservazioni*:
1. Se $A\in M_{n}(\mathbb C)$ è invertibile, allora esiste un'unica matrice $B\in M_{n}(\mathbb C)$ tale che $A\cdot B=\mathbb 1_{n}=B\cdot A$, detta **matrice inversa di A** e si indica con $A^{-1}$
2. **Non tutte le matrici quadrate sono invertibili** <br> *Esempio*: $A=\begin{pmatrix} & 1 & 0 &  \\  & 0 & 0\end{pmatrix}\in M_{2}(\mathbb C),\ A\ne \emptyset$ <br> Cerchiamo una matrice $B=\begin{pmatrix} & a & b &  \\  & c & d\end{pmatrix}$
3. È possibile dimostrare che $A\cdot B=\mathbb 1_{n}\Leftrightarrow B\cdot A=\mathbb 1_{n}$, cioè $B$ è inversa destra di $A$ *se e solo se* $B$ è inversa sinistra di $A$
4. La definizione di matrice invertibile si può dare in modo analogo anche per matrici non quadrate.
    - l'ordine del prodotto conta, quindi *inversa destra $\ne$ inversa sinistra*.
    - salta l'unicità *Esempio*: La matrice $\begin{pmatrix}1 \\ \alpha\end{pmatrix}$ è inversa destra della matrice $\begin{pmatrix}1 & 0\end{pmatrix}\forall \alpha\in\mathbb C$:<br> $\begin{pmatrix}1 & 0\end{pmatrix}\cdot \begin{pmatrix}1 \\ \alpha\end{pmatrix}=1$

**Proprietà della Matrice Inversa** di una matrice quadrata:
Siano $A,B\in M_{n}(\mathbb C)$ matrici invertibili. Allora:
1. $(A^{-1})^{-1}=A$
2. $A\cdot D$ è invertibile e $(A\cdot D)^{-1}=D^{-1}\cdot A^{-1}$

#### Teorema
Sia $A\in M_{n}(\mathbb C)$ una matrice quadrata. Allora le seguenti affermazioni sono equivalenti:
1. $A$ è invertibile
2. $A\cdot x=b$ ha un'unica soluzione per ogni $b\in \mathbb C^n$
3. una (ciascuna) forma ridotta di $A$ ha tutte le colonne dominanti
4. $rk(A)=n$

*Osservazioni*: le affermazioni 2,3,4 sono equivalenti. Se $A$ è invertibile allora esiste la sua inversa $A^{-1}\in M_{n}(\mathbb C)$ e $$\underbrace{A^{-1}\cdot A}_{\mathbb 1_{n}}\cdot x=A^{-1}\cdot b$$ cioè $x=A^{-1}\cdot b$  è l'*unica soluzione* del sistema.
Analogamente con ciò che avviene in $\mathbb C$: $a\in\mathbb C$ è invertibile in $\mathbb C\Leftrightarrow a\ne 0$ e in tal caso <br>$\frac{a}{a}\cdot x=\frac{b}{a}\ \Rightarrow\ x=\frac{b}{a}=a^{-1}\cdot b$  è l'*unica soluzione*.

*Proposizione*: Sia $A\in M_{m,n}(\mathbb C)$. Allora effettuando opportune **operazioni elementari sulle righe** di $A$ è possibile ottenere una *matrice a gradini* in cui le **colonne dominanti** hanno
- i Pivot uguali a 1
- tutti gli altri coefficienti uguali a 0
detta **Forma Ridotta di Gauss-Jordan di A**.

*Esempio*:$$\begin{align}
\begin{pmatrix}
 & 1 & \dots & \dots & \dots & \dots &  \\
  & 0 & 1 & \dots & \dots & \dots \\
   & 0 & 0 & 0 & 1 & \dots &  \\
    & 0 & 0 & 0 & 0 & 0 \\
\end{pmatrix} \\
\begin{matrix}
D &  D\ \   & L &\ \  D &\ \  L &  & 
\end{matrix}\end{align}$$
*Osservazione*: Se $A\in M_{n}(\mathbb C)$ è **invertibile**, allora una sua forma ridotta di Gauss ha tutte le colonne dominanti e quindi la sua forma ridotta di Gauss-Jordan è$$\mathbb 1_{n}=\begin{pmatrix}
 & 1 & 0 & \dots & 0 &  \\
  & 0 & 1 & \dots & \dots \\
   & 0 & 0 & \dots & \dots \\
    & \dots & \dots & \dots & \dots \\
     & 0 & 0 & 0 & 1
\end{pmatrix}$$
##### Strategia per determinare se una matrice è invertibile e trovarne l'inversa
Sia $A\in M_{n}(\mathbb C)$.
1. Consideriamo la matrice $(A|\mathbb 1_{n})\in M_{n,2n}(\mathbb C)$
2. Con opportune *operazioni elementari sulle righe*, otteniamo una forma ridotta di Gauss-Jordan$$(C|D)$$
3. Se $C=\mathbb 1_{n}$ allora $A$ è *invertibile* e l'inversa di $A$ è $A^{-1}=D$. Altrimenti $A$ non è *invetibile*

*Esercizio*: (calcolo inversa di matrice con parametro)

Sia $A(\alpha)=\begin{pmatrix} & \alpha-1 & 1 & \alpha-1 &  \\  & \alpha-1 & 1 & -1 \\  & 0 & 1 & 0\end{pmatrix}\in M_{3}(\mathbb R)$ <span>&emsp;</span> con $\alpha \in\mathbb R$.

Stabilire per quali $\alpha \in\mathbb R$ la matrice è invertibile e per questi valori calcolare l'inversa $A(\alpha)^{-1}$.$$\begin{align}
(A(\alpha)\ |\ \mathbb 1_{3})=&\begin{pmatrix}
 & \alpha-1 & 1 & \alpha-1 & | & 1 & 0 & 0 &  \\
  & \alpha-1 & 1 & -1 & | & 0 & 1 & 0 \\
& 0 & 1 & 0 & | & 0 & 0 & 1
\end{pmatrix} \\ \\
E_{21}(-1)\rightarrow&\begin{pmatrix}
 & \alpha-1 & 1 & \alpha-1 & | & 1 & 0 & 0 &  \\
  & 0 & 0 & -\alpha & | & -1 & 1 & 0 \\
   & 0 & 1 & 0 & | & 0 & 0 & 1
\end{pmatrix} \\ \\
E_{23}\rightarrow &\begin{pmatrix}
 & \alpha-1 & 1 & \alpha-1 & | & 1 & 0 & 0 &  \\
  & 0 & 1 & 0 & | & 0 & 0 & 1 \\
   & 0 & 0 & -\alpha & | & -1 & 1 & 0
\end{pmatrix}
\end{align}$$
**Caso 1**: $\alpha-1=0$ quindi $\alpha=1$ $$(C\ |\ d)=\begin{pmatrix}
 & \alpha-1 & 
\end{pmatrix}$$

**Caso 2**: $\alpha-1\ne 0$ cioè $\alpha\ne 1$ $$E_{1}\left( \frac{1}{\alpha-1} \right)\rightarrow\begin{pmatrix}
 & 1 & \frac{1}{\alpha-1} & 1 & | & \frac{1}{\alpha-1} & 0 & 0 &  \\
  & 0 & 1 & 0 & | & 0 & 0 & 1 \\
   & 0 & 0 & -\alpha & | & -1 & 1 & 0
\end{pmatrix}$$
**Caso 2a**: $-\alpha=0$ quindi $\alpha=0$ $$(C\ |\ D)=\begin{pmatrix}
 & 1 & -1 & 1 & | & -1 & 0 & 0 &  \\
  & 0 & 1 & 0 & | & 0 & 0 & 1 \\
   & 0 & 0 & 0 & | & 
\end{pmatrix}$$
**Caso 2b**: $\alpha\ne 1$ e $\alpha\ne 0$ $$E_{3}\left( \frac{1}{-\alpha} \right)\rightarrow \begin{pmatrix}
 & 1 & \frac{1}{\alpha-1} & 1 & | & \frac{1}{\alpha-1} & 0 & 0 &  \\
  & 0 & 1 & 0 & | & 0 & 0 & 1 \\
   & 0 & 0 & 1 & | & \frac{1}{\alpha} & -\frac{1}{\alpha} & 0
\end{pmatrix}$$Notiamo che in questo caso $A$ è invertibile. Troviamo una forma di Gauss-Jordan di $A$ (trasformiamo la matrice a sinistra di $|$ in $\mathbb 1_{3}$) per determinare $A^{-1}$.$$\begin{align}
E_{12}\left( -\frac{1}{\alpha-1} \right)\rightarrow \begin{pmatrix}
 & 1 & 0 & 1 & | & \frac{1}{\alpha-1} & 0 & -\frac{1}{\alpha-1} &  \\
 & 0 & 1 & 0 & | & 0 & 0 & 1 \\
  & 0 & 0 & 1 & | & \frac{1}{\alpha} & -\frac{1}{\alpha} & 0
\end{pmatrix} \\ \\
E_{13}(-1)\rightarrow \begin{pmatrix}
 & 1 & 0 & 0 & | & \frac{1}{\alpha-1}-\frac{1}{\alpha} & \frac{1}{\alpha} & -\frac{1}{\alpha-1} &  \\
  & 0 & 1 & 0 & | & 0 & 0 & 1 \\
   &0 & 0 & 1 & | & \frac{1}{\alpha} & -\frac{1}{\alpha} & 0
\end{pmatrix}\end{align}$$L'inversa di $A$ è quindi la matrice a destra della barra$$A^{-1}=\begin{pmatrix}
& \frac{1}{\alpha-1}-\frac{1}{\alpha} & \frac{1}{\alpha} & -\frac{1}{\alpha-1} & \\
 & 0 & 0 & 1 \\
  & \frac{1}{\alpha} & -\frac{1}{\alpha} & 0
\end{pmatrix}$$(che esiste solo per $\alpha\ne0\ne 1$)

### Matrici Diagonali, Scalari e Triangolari
*Definizione*: Sia $A=(a_{ij})\in M_{n}(\mathbb C)$ una matrice quadrata. La **diagonale principale** di $A$ è l'n-upla ordinata$$(a_{11}\ a_{22}\ a_{33}\ \dots\ a_{nn})$$
*Definizione*: una matrice quadrata $A\in M_{n}(\mathbb C)$ si dice 
- **MATRICE DIAGONALE**: se tutti i coefficienti fuori dalla *diagonale principale* sono nulli
- **MATRICE SCALARE**: se $A=\alpha \cdot \mathbb 1_{n}=\begin{pmatrix} & \alpha & 0 & \dots & 0  & \\  & 0 & \dots & \dots & \dots \\  & 0 & \dots & 0 & \alpha\end{pmatrix}$ per un qualche $\alpha\in\mathbb C$
- **MATRICE TRIANGOLARE SUPERIORE**: se tutti i coefficienti al di sotto della diagonale principale sono nulli

*Esempi*:
1. $\begin{pmatrix} & 5 & 0 \\  & 0 & i\end{pmatrix}$ è diagonale
2. $\mathbb 1_{n}$ è scalare
3. $\begin{pmatrix} & 2 & 0 & 0 &  \\  & 0 & 2 & 0 &  \\  & 0 & 0 & 2\end{pmatrix} = 2\cdot\mathbb 1_{3}$ è scalare
4. $\begin{pmatrix} & 1 & 2 & 0 &  \\  & 0 & 0 & i \\  & 0 & 0 & -1\end{pmatrix}$ è triangolare superiore
5. Una matrice quadrata a gradini è triangolare superiore

#### Proprietà matrici scalari
Sia $A=\alpha \cdot\mathbb 1_{n}\in M_{n}(\mathbb C)$ una matrice scalare e siano $B,C\in M_{n}(\mathbb C)$. Allora 
1. $A\cdot B=(\alpha \cdot\mathbb 1_{n})\cdot B=\alpha \cdot(\mathbb 1_{n}\cdot B)=\alpha \cdot B$
2. $C\cdot A=C\cdot(\alpha \cdot\mathbb 1_{n})=\alpha \cdot(C\cdot \mathbb 1_{n})=\alpha \cdot C$

Cioè nel prodotto righe per colonne, le matrici scalari $\alpha \cdot\mathbb 1_{n}$ si comportano come numeri $\alpha\in\mathbb C$.

### Matrici Trasposta, Coniugata e H-Trasposta
*Definizione*: Sia $A=(a_{ij})\in M_{m,n}(\mathbb C)$ una matrice
- la **trasposta** di $A$ è la matrice: $$A^T=(b_{ij})\in M_{n,m}(\mathbb C)$$dove $b_{ij}=a_{ji}\quad\forall 1\le i\le n,\ 1\le j\le m$.<br>*Esempio*:$$A=\begin{pmatrix}
1 & 3+i \\
i & -1 \\
0 & 2i
\end{pmatrix}\in M_{3,2}(\mathbb C)\quad A^T=\begin{pmatrix}
1 & i & 0 \\
3+i & -1 & 2i
\end{pmatrix}\in M_{2,3}(\mathbb C)$$

- la **coniugata** di $A$ è la matrice:$$\bar{A}=(\bar{a_{ij}})\in M_{m,n}(\mathbb C)$$*Esempio*:$$A=\begin{pmatrix}
1 & i & 0 \\
3+i & -1 & 2i
\end{pmatrix}\in M_{2,3}(\mathbb C)\quad \bar{A}=\begin{pmatrix}
1 & -i & 0 \\
3-i & -1 & -2i
\end{pmatrix}\in M_{2,3}(\mathbb C)$$
- la **H-trasposta** di $A$ è la matrice:$$A^H=\bar{(A^T)}=(\bar{A})^T\in M_{}$$*Esempio*:$$A=\begin{pmatrix}
1 & 3+i \\
i & -1 \\
0 & 2i
\end{pmatrix}\quad A^H=(\bar{A})^T=\begin{pmatrix}
1 & 3-i \\
-i & -1 \\
0 & -2i
\end{pmatrix}^T=\begin{pmatrix}
1 & -i & 0 \\
3-i & -1 & -2i
\end{pmatrix}\in M_{2,3}(\mathbb C)$$
<br>
**Proprietà**:
Siano $A,B$ matrici  e $\alpha\in\mathbb C$ un numero. si supponga che le somme e i prodotti indicati esistano.
1. $\frac{(A^T)^T}{\bar{A}}\Rightarrow(A^H)^H=A$
2. $\frac{(\alpha \cdot A)^T}{\alpha \cdot A}\Rightarrow(\alpha \cdot A)^H=\bar{\alpha}\cdot A^H$
3. $\frac{(A^{-1})^T}{(A^{-1})}\Rightarrow (A^{-1})^H=(A^H)^{-1}$
4. $\frac{(A+B)^T}{A+B}\Rightarrow(A+B)^H=A^H+B^H$
5. $\frac{(A\cdot B)^T}{A\cdot B}\Rightarrow(A\cdot B)^H=B^H\cdot A^H$

*Esempio*: $A=\begin{pmatrix}1 & i \\ 0 & -1\end{pmatrix}\in M_{2}(\mathbb C),\ B=\begin{pmatrix}2 \\ 0\end{pmatrix}\in\mathbb C^2$ $$\begin{align}
 & A\cdot B=\begin{pmatrix}
 1 & i \\
 0 & -1
 \end{pmatrix}\cdot \begin{pmatrix}
 2 \\
 0
 \end{pmatrix}=\begin{pmatrix}
 2 \\
 0
 \end{pmatrix}\in\mathbb C^2 \\
  & (A\cdot B)^T=\begin{pmatrix}
  2 & 0
  \end{pmatrix}\in\mathbb C_{2} \\ 
   & B^T=\begin{pmatrix}
  2 & 0
  \end{pmatrix}\in \mathbb C_{2},\ A^T\begin{pmatrix}
  1 & 0 \\
  i & -1
  \end{pmatrix}\in M_{2}(\mathbb C) \\
   & B^T\cdot A^T=\begin{pmatrix}
   2 & 0
   \end{pmatrix}\cdot \begin{pmatrix}
   1 & 0 \\
   i & -1
   \end{pmatrix}=\begin{pmatrix}
   2 & 0
   \end{pmatrix}\in\mathbb C_{2}
\end{align}$$il prodotto $A^T\cdot B^T$ non è definito.

*Definizione*: una matrice $A\in M_{m,n}(\mathbb C)$ è detta:
- **simmetrica** se $A=A^T$
- **antisimmetrica** se $A=-A^T$
- **hermitiana** se $A=A^H$
- **antihermitiana** se $A=-A^H$

*Esempi*:
1. $A=\begin{pmatrix}1 & -i \\ -i & 2\end{pmatrix}$ è *simmetrica*
2. $A=\begin{pmatrix}0 & 1 \\ -1 & 0\end{pmatrix}$ è *antisimmetrica*
3. $A=\begin{pmatrix}1 & 1-i \\ 1+i & 2\end{pmatrix}$ è *hermitiana*
4. $A=\begin{pmatrix}2i & 1-i \\ -1-i & -i\end{pmatrix}$ è *antiherimitiana*

*Osservazioni*:
1. Se $A$ soddisfa una delle definizione precedenti allora $A$ è *matrice quadrata*. (infatti se $A\in M_{m,n}(\mathbb C),\ A^T,A^H\in M_{n,m}(\mathbb C)$)
2. Se $A$ è *antisimmetrica* allora la diagonale principale di $A$ è uguale alla diagonale principale di $-A^T$ cioè$\begin{cases}a_{11}=-a_{11} \\ a_{22}=-a_{22} \\ \dots \\ a_{nn}=-a_{nn}\end{cases}$
3. Se $A$ è *antihermitiana* allora diagonale principale di $A$ è uguale alla diagonale principale di $-A^H$ cioè $\begin{cases}a_{11}=-\bar{a_{11}} \\ a_{22}=-\bar{a_{22}} \\ \dots \\ a_{nn}=-\bar{a_{nn}}\end{cases}$<br> Dunque una matrice *antihermitiana* ha tutti i valori nella diagonale principale uguali a 0 oppure immaginari puri.

### Determinante di Matrici Quadrate
Sia $A\in M_{n}(\mathbb C)$.
Il **determinante** di $A$, indicato con $\det(A)$ o $Det(A)$, è un numero che dipende da $A$.
- se $n=1,\ A=(a_{11})$ allora $\det(A)=a_{11}$
- se $n=2,\ A=\begin{pmatrix}a_{11} & a_{12} \\ a_{21} & a_{22}\end{pmatrix}$
$$\det(A)=(a_{11}\cdot a_{22}-a_{12}\cdot a_{21})$$

*Definizione*: Data $A\in M_{n}(\mathbb C)$ la **matrice complementare di posto** $i_{ij}$ di $A$ è la matrice $C_{ij}\in M_{n-1}(\mathbb C)$ che si ottiene togliendo la $i$-esima riga e la $j$-esima colonna di $A$.

*Esempio*: $$A=\begin{pmatrix}
1 & 0 & -1 \\
0 & 2 & 3 \\
-2 & i & 0
\end{pmatrix}\in M_{3}(\mathbb C)$$
$C_{11}=\begin{pmatrix}2 & 3 \\ i & 0\end{pmatrix}\qquad C_{12}=\begin{pmatrix}0 & 3 \\ -2 & 0\end{pmatrix}$

*Definizione*: Data $A\in M_{n}(\mathbb C)$ il **cofattore** di posto $(i,j)$ di $A$ è il numero$$A_{ij}=(-1)^{i+j}\cdot \det(C_{ij})$$
*Nota*: $(-1)^{i+j}\rightarrow \begin{pmatrix}+ & - & + & - & \dots \\ - & + & - & + & \dots \\ \dots\end{pmatrix}$
*Esempio*: $\qquad A=\begin{pmatrix}1 & 0 & -1 \\ 0 & 2 & 3 \\ -2 & i & 0\end{pmatrix}$
$A_{11}=(-1)^{1+1}\cdot \det \begin{pmatrix}2 & 3 \\ i & 0\end{pmatrix}=(+1)\cdot[2\cdot0-3\cdot i]=-3i$
$A_{12}=(-1)^{1+2}\cdot \det \begin{pmatrix}0 & 3 \\ -2 & 0\end{pmatrix}=(-1)\cdot[0\cdot0-(3\cdot(-2))]=-6$

### Formula Calcolo del Determinante
**Rispetto alla prima riga (sviluppo di Laplace)**
Se $A=(a_{ij})\in M_{n}(\mathbb C)$, allora:
$\det(A)=\begin{pmatrix}a_{11} & a_{12} & \dots & a_{1n}\end{pmatrix}\cdot \begin{pmatrix}A_{11} \\ A_{12} \\ \dots \\ A_{1n}\end{pmatrix}$ cofattori di post $1,j$
**Teorema**: Sia $A\in M_{n}(\mathbb C),\ A=(a_{ij})$ Allora$$\begin{align}
\det(A)&=\begin{pmatrix}
a_{i1} & a_{i2} & \dots & a_{in}
\end{pmatrix}\cdot \begin{pmatrix}
A_{i1} \\
A_{i 2} \\
\dots \\
A_{in}
\end{pmatrix} \\
 & =\begin{pmatrix}
 A_{1j} & A_{2j} & \dots & A_{nj}
 \end{pmatrix}\cdot \begin{pmatrix}
 a_{1j} \\
 a_{2j} \\
 \dots \\
 a_{nj}
 \end{pmatrix}\end{align}$$
*Osservazione*: possiamo calcolare il *determinante* utilizzando una riga o colonna con tanti zeri.

*Osservazione*: Se $A\in M_{n}(\mathbb C)$ ha una riga o colonna nulla, allora $det(A)=0$.

**Proposizione**: Se $A=\begin{pmatrix}a_{ij}\end{pmatrix}\in M_{n}(\mathbb C)$ è *triangolare superiore* allora $\det(A)=a_{11}\cdot a_{22}\cdot\dots \cdot a_{nn}$

*Nota*: Si dimostra calcolando ripetutamente lo *sviluppo di Laplace* rispetto alla prima colonna$$A=\begin{pmatrix}
a_{11} & * & \dots & * \\
0 & a_{22} & \dots & \dots \\
\dots & 0 & \dots & * \\
0 & 0 & 0 & a_{nn}
\end{pmatrix}$$
*Esempi*:
- $\det(\mathbb 1_{n})=\det \begin{pmatrix}1 &  &  \\  & \dots &  \\  &  & 1\end{pmatrix}$


