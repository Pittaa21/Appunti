Tecnica per calcolare quanti elementi ha un dato insieme.

#### Principio di Additività o Addizione
Se ho $n$ insiemi disgiunti allora $|\text{I}|$ è il numero di elementi $$|\text{U}^n_{j=1}\ \text{I}_{j}|=\sum_{j=1}^n|\text{I}_{j}|$$

Se abbiamo $n$ insiemi (non necessariamente disgiunti) posso sempre renderli disgiunti
*Esempio*:
$I_{1},I_{2},I_{3}$
$I_{1}'=I_{1}/(I_{2}\cup I_{3})$
$I_{1}'$ è disgiunto da $I_{2},I_{3}$

#### Principio di Moltiplicazione
Esperimenti **indipendenti** e **ripetuti**.

- **indipendenti**: il risultato del successivo non dipende dal risultato del precedente, se i risultati del $j$-esimo *esperimento* sono $r_j$ allora tutti i possibili risultati sono: $$r_{1}\cdot r_{2}\cdot r_{3} \cdot r_{n}=\pi^n_{j=1}r_{j}$$Dove $n$ è il numero di esperimenti<br>*Esempio*: Abbiamo tre dadi uno con 6 facce uno con 8 e uno con 20<br>$6\cdot8\cdot 20$

##### Permutazioni di un insieme
*Def*: La permutazione è una disposizione ordinata di $n$ oggetti distinti $\in \mathbb N$.

Abbiamo un insieme $A$ che contiene $n$ elementi (disgiunti e diversi) $A=\{a_{1},a_{2},a_{n}\}$ 
creare una $n$-upla (un vettore di $n$ componenti **ordinato**)
Quante permutazioni di $A$ ?
$n\cdot(n-1)\cdot(n-2)\cdot\ \dots\ \cdot2\cdot1=n! =n$-fattoriale  

Numero di permutazioni di un insieme di $n$ elementi **disgiunti** è $n!$


##### $r$-permutazioni
Abbiamo un insieme di $n$ elementi diversi e vogliamo determinare una $$\frac{n\cdot(n-1)\cdot(n-2)\cdot\ \dots\ \cdot 2\cdot 1}{(n-r)\cdot(n-r-1)\cdot\ \dots\ \cdot 2 \cdot 1}$$
##### $r$-combinazioni
Dato un insieme di $n$ elementi **diversi**$$A=\{a_{1},\dots,a_{n}\}$$Una $r$-combinazione è un sottoinsieme di $r$-elementi di $A$.
*Nota*: $r\le n$, sottoinsieme $\Rightarrow$ $r$-upla non-ordinata.

data una $r$-permutazione questa induce una $r$-combinazione$$\left(a_{i_{1}},a_{i_{2}},\dots,a_{i_{r}}\right)\rightarrow\left\{a_{i_{1}},a_{i_{2}},\dots,a_{i_{r}}\right\}$$
numero di $r$-combinazioni=$\frac{n!}{(n-r)!\cdot r!}$ 

*Esempio*: calcolare probabilità di fare cinquina al lotto
$\large\frac{90!}{85!\cdot 5!}$

$c(n,r)=\binom nr=\frac{n!}{(n-r)!\cdot r!}$


$(a+b)^n=(a+b)(a+b)\dots(a+b)$
Tutte le $2^n$ possibili strighe:
$\sum_{k=0}^na^k\cdot b^{n-k}$
Quindi $(a+b)^n=\sum^n_{k=0}\binom nka^k\cdot b^{n-k}$

- Tramite la formula binomiale:$$(1+x)^n=\sum_{k=0}^n\binom nk x^k\approx \sum_{k=0}^T\binom nkx^k$$$T=0\Rightarrow(1+x)^n\approx 1\approx f(0)$<br>$T=1\Rightarrow(1+x)^n\approx 1+nx\approx f(0)+f'(0)x$<br>$T=t\Rightarrow(1+x)^n\approx a+nx+\dots+\binom ntx^t$

Probabilità binomiali
$(1)^n=(p+(1-p))^n\Rightarrow\binom nkp^k(1-p)^{n-k}$<br>Se $p=\frac{1}{2}$ e $(1-p)=\frac{1}{2}$<br>$(1)^n=1=\sum^n_{k=0}\binom nk\left( \frac{1}{2} \right)^k\left( \frac{1}{2} \right)^{n-k}=\sum^n_{k=0}\binom nk=2^n$

1. Dato $0\le k\le n$, vale$$\binom nk=\binom n{n-k}$$
2. Dato $0\le m\le k\le n$, vale$$\binom nk\cdot\binom km=\binom nm\cdot\binom {n-m}{k-m}$$
$\binom nk\Rightarrow$ numero stringhe di $n$ elementi

3. Dato $1\le k\le n$ vale$$\begin{align}
 &\frac{n!}{k!(n-k)!}=\binom nk=\binom {n-1}{k-1}+\binom {n-1}k \\
 &=\frac{(n-1)!}{(k-1)!(n-k)!}+\frac{(n-1)!}{k!(n-k-1)!} \\
 & (n-1)!\cdot\left( \frac{n}{k!(n-k)!} \right) \\
  & =\frac{n(n-1)!}{k!(n-k)!}=\frac{n!}{k!(n-k)!}=\binom nk
\end{align}$$Quindi $\large\binom{n-1}{k-1}+\binom{n-1}k=\binom nk$

**Triangolo di Tartaglia**
img

Dato un insieme di $n$ elementi diviso in $k$ categorie identificabili. Quante *permutazioni* si possono creare. $A=\cup^k_{j=1}A_{j}$
ogni $A_{j}\cap A_{i}=\emptyset$ con $j\ne i$
$|A|=n_{1}\quad|A_{j}|=r_{j}\quad\sum^k_{j=1}r_{j}=n$ 
- Considero gli elementi di ogni $A_{j}$ come identificabili quindi ci sono $n!$ possibili permutazioni.<br><br>Se gli elementi di $A_{1}$ sono identificabili $\frac{n!}{r_{1}!}$<br>itero su $j=r_{1},\dots,k$ <br>$\large\binom n{r_{1},r_{2},\dots,r_{k}}=\frac{n!}{r_{1}!r_{2}!\dots r_{k}!}\in\mathbb N$

*Esempio*: Quante soluzioni intere ha $x_{1}+x_{2}+x_{3}=5$ infinite. Invece, se $x_{1}\ge0,\ x_{2}\ge 0,\ x_{3}\ge 0$ quindi $x_{1},x_{2},x_{3}$ sono interi positivi $x_{1}+x_{2}=5$ ha 6 soluzioni.


- $r$-permutazioni: disposizioni ordinate di $r$ oggetti distinti su $n$ possibili *disposizioni*$$\frac{n!}{r!}$$
- $r$-combinazioni: selezione non-ordinata di $n$ oggetti distinti su $n$ possibili *combinazioni*$$\binom nr=\frac{n!}{r!(n-r)!}$$
*Esempio*: 11 domande a risposta multipla con 2 alternative per avere 5 risposte corrette ho $\binom {11}5$ che equivale a $\binom {11}6$ sbagliate