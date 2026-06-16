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
Sono relazioni di ricorrenza in cui $a_{n}$ viene espresso