*Def*: Tecnica per calcolare quanti elementi ha un dato insieme.

### Principio di Additività o Addizione
Se ho $n$ insiemi disgiunti allora $|\text{I}|$ è il numero di elementi $$|\text{U}^n_{j=1}\ \text{I}_{j}|=\sum_{j=1}^n|\text{I}_{j}|$$

Se abbiamo $n$ insiemi (non necessariamente disgiunti) posso sempre renderli disgiunti
*Esempio*:
$I_{1},I_{2},I_{3}$
$I_{1}'=I_{1}/(I_{2}\cup I_{3})$
$I_{1}'$ è disgiunto da $I_{2},I_{3}$

### Principio di Moltiplicazione
Esperimenti **indipendenti** e **ripetuti**.

- **indipendenti**: il risultato del successivo non dipende dal risultato del precedente, se i risultati del $j$-esimo *esperimento* sono $r_j$ allora tutti i possibili risultati sono: $$r_{1}\cdot r_{2}\cdot r_{3} \cdot r_{n}=\pi^n_{j=1}r_{j}$$Dove $n$ è il numero di esperimenti<br>*Esempio*: Abbiamo tre dadi uno con 6 facce uno con 8 e uno con 20<br>$6\cdot8\cdot 20$

### Permutazioni di un insieme
*Def*: La ***permutazione*** è una disposizione ==ordinata== di $n$ oggetti distinti $\in \mathbb N$.

Abbiamo un insieme $A$ che contiene $n$ elementi (disgiunti e diversi) $A=\{a_{1},a_{2},a_{n}\}$ 
creare una $n$-upla (un vettore di $n$ componenti **ordinato**)
Quante permutazioni di $A$ ?
$\text{P}(n,n)=n\cdot(n-1)\cdot(n-2)\cdot\ \dots\ \cdot2\cdot1=n! =n$-fattoriale  

Numero di permutazioni di un insieme di $n$ elementi **disgiunti** è $n!$


#### $r$-permutazioni
Dati $n$ oggetti *distinti*, con $n,r\in\mathbb N$, $r\le n$
Una $r$**-permutazione** è una disposizione ordinata di questi $n$ oggetti usando $r$ degli $n$ oggetti.
Il numero di tutte le possibili $r$**-permutazioni** di $n$ oggetti è:$$\text{P}(n,r)=n\cdot(n-1)\cdot(n-2)\cdot\ \dots\ \cdot (n-r+1)$$Quindi$$\text{P}(n,r)=\frac{n!}{(n-r)!}$$
#### $r$-combinazioni
Selezione *non ordinata* di $r$ degli $n$ oggetti (un sottoinsieme di $r$ oggetti dell'insieme di $n$ oggetti) e si indica con $\text{C}(n,r)$.$$C(n,r)=\frac{P(n,r)}{r!}=\frac{n!}{(n-r)!\ r!}=\binom nr$$

Dato un insieme di $n$ elementi **diversi**$$A=\{a_{1},\dots,a_{n}\}$$Una $r$-combinazione è un sottoinsieme di $r$-elementi di $A$.

*Nota*: $r\le n$, sottoinsieme $\Rightarrow$ $r$-upla non-ordinata.
Data una $r$-permutazione questa induce una $r$-combinazione$$\left(a_{i_{1}},a_{i_{2}},\dots,a_{i_{r}}\right)\rightarrow\left\{a_{i_{1}},a_{i_{2}},\dots,a_{i_{r}}\right\}$$
*Esempio*: calcolare probabilità di fare cinquina al lotto
$\large\frac{90!}{85!\cdot 5!}$

$c(n,r)=\binom nr=\frac{n!}{(n-r)!\cdot r!}$


#### Formula Binomiale
$\forall a,b\in\mathbb Z,\ n\in\mathbb N$$$(a+b)^n=\sum_{k=0}^n\binom nk\cdot a^{n-k}\cdot b^k$$
#### Identità Binomiali
$n,k\in\mathbb N,\ k\leq n$
1. $\LARGE\binom nk=\binom n{n-k}$
2. $\LARGE\binom nk=\binom {n-1}k+\binom {n-1}{k-1}$ per $k\leq n-1$
3. $0\le m\le k\leq n$ $\LARGE\binom nk\cdot\binom km=\binom nm \cdot\binom {n-m}{k-m}$

**Triangolo di Tartaglia**
img


Una ***permutazione con ripetizioni*** è una **disposizione** ordinata di oggetti dei quali alcuni non sono distinguibili.

###### Teorema
Dati $n$ oggetti, di cui
$r_{1}$ del tipo 1
...
$r_{m}$ del tipo $m$
con $r_{1}+\dots+r_{m}=n$, il numero delle permutazioni di questi $n$ oggetti è:$$P(n;r_{1},\dots,r_{m})=\binom n{r_{1}}\cdot\binom{n-r_{1}}{r_{2}}\dots\binom{r_{m}}{r_{m}}=\frac{n!}{r_{1}!\cdot r_{2}!\dots r_{m}!}$$
#### Relazioni di Ricorrenza
Una ***relazione di ricorrenza*** è una formula ricorsiva che conta il numero di modi d'eseguire una procedura con $n$ oggetti in funzione del numero di modi d'eseguirla con un numero minore di oggetti.
$a_{k}=$ il numero di modi di eseguire la procedura con $k$ oggetti
$k=0,1,2,3,\dots$

Una **relazione di ricorrenza** è una formula che esegue $a_{n}$ in funzione di alcuni degli $a_{k},\ k<n$.

*Esempio*: $a_{n}=2\cdot a_{n-1}$
non si può calcolare $a_{n}$ ricorsivamente se non abbiamo delle ==condizioni iniziali==.
occorre avere un valore per $a_{0}$ (*condizione iniziale*). 
Per esempio: se $a_{0}=1$ allora $a_{1}=2\cdot{1}=2$, $a_{2}=2\cdot 2=4$, $a_{3}=2\cdot 2^2=2^3\ \dots$

**La soluzione** di una ***relazione di ricorrenza*** è una formula esplicita per $a_{n}$ che dipende solo da $n$.

##### Relazioni di ricorrenza lineari omogenee
Sono ***relazioni di ricorrenza*** in cui $a_{n}$ viene espresso ==solo== in funzione di alcuni degli $a_{k}$ con $k<n$.
Sono del tipo:$$a_{n}=c_{1}\cdot a_{n-1}+c_{2}\cdot a_{n-2}+\dots+c_{r}\cdot a_{n-r}$$dove $c_{1},\dots,c_{r}$ sono costanti e $c_{r}\neq{0}$
Per poterle risolvere servono $r$ *condizioni iniziali* che permettono di calcolare $c_{1},\dots,c_{r}$
$r=$ ***grado*** della **relazione di ricorrenza**

###### Per risolverle:
1. Porre $x^k$ al posto di $a_{k}$ nella relazione$$x^n=c_{1}x^{n-1}+c_{2}x^{n-2}+\dots+c_{2}x^{n-r}$$
2. Dividere per $x^{n-r}$ $$x^r=c_{1}x^{r-1}+c_{2}x^{r-2}+\dots+c_{r-1}x+c_{r}$$
3. L'*equazione caratteristica* della relazione è:$$x^r-c_{1}x^{r-1}-\dots-c_{r-1}x-c_{r}=0$$Siano $\alpha_{1},\dots,\alpha_{k}$ le soluzioni ==distinte== dell'eq. caratteristica con molteplicità $m_{1},\dots,m_{k}$:$$0=(x-\alpha_{1})^{m_{1}}\dots(x-\alpha_{k})^{m_{k}}$$$m_{1}+\dots+m_{k}=r$
4. La **soluzione generale** della relazione di ricorrenza è l'***insieme delle combinazioni lineari*** delle seguenti soluzioni.$$\begin{align}
 & \alpha_{1}^n,n\alpha_{1}^n,n^2\alpha_{1}^{n},\dots,n^{m_{1}-1}\alpha_{1}^n \\
  & \dots \\
   & \alpha_{k}^n,n\alpha_{k}^n,n^2\alpha_{k}^{n},\dots,n^{m_{k}-1}\alpha_{k}^n
\end{align}$$
La soluzione generale è:$$a_{n}=A_{1}\alpha_{1}^n+A_{2}n\alpha_{1}^n+\dots+A_{m_{1}}n^{m_{1}-1}\alpha_{1}^n+A_{m_{1}+1}\alpha_{2}^n+\dots+A_{r}n^{m_{k}-1}\alpha_{k}^n$$dove $A_{1},A_{2},\dots,A_{r}$ sono costanti.

5. A questo punto decidiamo il valore delle costanti imponendo le $r$ *condizioni iniziali*.


##### Relazioni di ricorrenza lineari non omogenee di grado 1
Sono **relazioni di ricorrenza** del tipo:$$\circledast\qquad a_{n}=c\cdot a_{n-1}+f(n)$$con $c$ costante, $c\neq 0$ e $f(n)$ una funzione (in $n$)

###### Per risolverle:
1. Si trova la soluzione generale delle relazioni di ricorrenza omogenee associate a $\circledast$, cioè:$$\circledast\circledast\qquad a_{n}=c\cdot a_{n-1}$$Sol. gen. di $\circledast\circledast$: $A\cdot c^n$ dove $A$ è una costante che determineremo solo alla fine
2. Si somma alla soluzione generale di $\circledast\circledast$, cioè $A\cdot c^n$, una *soluzione particolare* $p(n)$ di $\circledast$<br>La **soluzione generale** di $\circledast$ è:$$A\cdot c^n+p(n)$$
3. Le constanti vengono determinate alla fine imponendo le condizioni iniziali