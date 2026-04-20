Tecnica per calcolare quanti elementi ha un dato insieme.

#### Principio di Additività
Se ho $n$ insiemi disgiunti allora $|\text{I}|$ è il numero di elementi $$|\text{U}^n_{j=1}\ \text{I}_{j}|=\sum_{j=1}^n|\text{I}_{j}|$$

Se abbiamo $n$ insiemi (non necessariamente disgiunti) posso sempre renderli disgiunti
*Esempio*:
$I_{1},I_{2},I_{3}$
$I_{1}'=I_{1}/(I_{2}\cup I_{3})$
$I_{1}'$ è disgiunto da $I_{2},I_{3}$

#### Principio di Moltiplicazione
Esperimenti **indipendenti** e **ripetuti**.

- **indipendenti**: il risultato del successivo non dipende dal risultato del precedente, se i risultati del $j$-esimo *esperimento* sono $r_j$ allora tutti i possibili risultati sono: $$r_{1}\cdot r_{2}\cdot r_{3} \cdot r_{n}=\pi^n_{j=1}r_{j}$$Dove $n$ è il numero di esperimenti<br>*Esempio*: Abbiamo tre dati uno con 6 facce uno con 8 e uno con 20<br>$6\cdot8\cdot 20$

##### Permutazioni di un insieme
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
