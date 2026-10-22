# Algoritmi

**Marco Pittarello**

==Definizione==: Procedura che con semplici istruzioni descrive come risolvere un problema.

Di ogni algoritmo bisogna sapere:
- Correttezza
- Stabilità
- Complessità

---

## Insertion Sort

> [!info] Idea
> Si costruisce incrementalmente un sottoarray ordinato `A[1..j-1]`.  
> A ogni passo si inserisce `A[i]` nella posizione corretta.

[animazione](https://upload.wikimedia.org/wikipedia/commons/9/9c/Insertion-sort-example.gif)

### Pseudocodice

```c++
InsertionSort(A)     //c0
    m = A.length     //c1
    for j = 2 to m   //nc2
        key = A[j]   //(n-1)c3
        i = j - 1    //(n-1)c4
        while i > 0 && A[i] > key // sum (t_j+1)c5
            A[i + 1] = A[i]       // sum t_j c6
            i = i - 1             // sum t_j c7
        A[i + 1] = key            //(n-1)c8
```

Tutte le operazioni elementari (assegnazione, operazioni aritmetiche) hanno costo costante. I cicli invece hanno il costo di una sommatoria $\sum$.

### Analisi

Efficiente per piccole quantità di dati, è uno degli algoritmi più semplici.
- Modello di calcolo: operazioni elementari a costo costante.
- Dimensione del problema: numero di elementi $n$.

$$
T^{IS}(n)= c_0+c_1+n c_2+(c_3+c_4+c_8)(n-1)
+\sum_{j=2}^n (t_j+1)c_5
+\sum_{j=2}^n t_j(c_6+c_7)
$$
dove $t_j$ è il numero di iterazioni del `while` per l'indice $j$.

> [!warning] Problemi
> - Troppe costanti ignote.
> - Dipende dalla specifica istanza del problema.

### Casi

| Caso | Condizione | $t_j$ | Complessità |
|---|---|---|---|
| Migliore | array già ordinato | $0$ | $T_{IS}^{min}(n)=a n+b=\Theta(n)$ |
| Peggiore | array ordinato al contrario | $j-1$ | $T_{IS}^{max}(n)=a n^2+bn+c=\Theta(n^2)$ |
| Medio | mediamente | $\frac{j-1}{2}$ | $\Theta(n^2)$ |

==Osservazione==: solitamente il caso medio coincide con quello peggiore.
Dato che ci sono 2 cicli il caso peggiore e quello medio avrà complessità $n^2$.

---

## Merge Sort

> [!info] Divide et Impera
> - **Divide**: divide il problema in sottoproblemi.
> - **Impera**: risolve ricorsivamente i sottoproblemi.
> - **Combina**: fonde le soluzioni in una soluzione del problema originale.

[animazione](https://commons.wikimedia.org/wiki/File:Merge-sort-example-300px.gif)

### Pseudocodice

```c
MergeSort(A, p, r)
    if p < r
        q = (p + r)/2
        MergeSort(A, p, q)
        MergeSort(A, q + 1, r)
        Merge(A, p, q, r)
```

```c
Merge(A, p, q, r)   // Pre: A[p..q] e A[q+1..r] sono ordinati.  
    n1 = q - p + 1  // Post: A[p..r] è ordinato.
    n2 = r - q

    for i = 1 to n1
        L[i] = A[p + i - 1]
    for j = 1 to n2
        R[j] = A[q + j]

    L[n1 + 1] = +∞
    R[n2 + 1] = +∞

    i = j = 1
    for k = p to r
        if L[i] <= R[j]
            A[k] = L[i]
            i++
        else
            A[k] = R[j]
            j++
```

### Correttezza

- Si dimostra per induzione su $l = r-p$.
- **Base** $l=0$: `p = r`, `A[p..p]` un solo elemento $\Rightarrow$ già ordinato.
- **Passo** $l>0\ (p<r)$: si divide `A[p..r]` in due parti. Per ipotesi induttiva, `MergeSort` ordina `A[p..q]` e `A[q+1..r]`. `Merge` opera sui due sottoarray ordinati e, soddisfatta la precondizione, produce `A[p..r]` ordinato.

### Analisi

- Spazio occupato in memoria: $a\cdot n+b$  
  $a$ = spazio occupato da un elemento dell'array (`int` 4 byte)  
  $n$ = numero di elementi dell'array  
  $b$ = spazio occupato dagli *elementi di controllo* (`if`, `for`)

- Ricorrenza:
  $$
  T^{MS}(n)=
  \begin{cases}
  c_0 & n \le 1\\[4pt]
  T^{MS}\!\left(\left\lfloor \frac{n}{2}\right\rfloor\right)
  +T^{MS}\!\left(\left\lceil \frac{n}{2}\right\rceil\right)
  +an+b & n>1
  \end{cases}
  $$

#### Albero di ricorsione
- altezza: $h=\log_2 m$
- costo a livello $j$: $am+2^j b$
- numero foglie: $m c_0$

$$
\begin{aligned}
T^{MS}(n)
&= \left(\sum_{j=0}^{h-1}an+2^j b\right)+n c_0 \\
&=ahn+\left(2^h-1\right)b+nc_{0}\\
&= an\log_2 n+(n-1)b+n c_0 \\
&\approx \Theta(n\log n)
\end{aligned}
$$

### Confronto Insertion Sort vs Merge Sort

> [!tip] Interpretazione
> Per $n$ grandi, MergeSort è asintoticamente migliore.  
> Per $n$ piccoli, InsertionSort può essere più veloce per via delle costanti inferiori.
> $$
> \begin{aligned}
> T^{IS}(n)\ &\approx\ n^2 \\
> T^{MS}(n)\ &\approx\ n\log n
> \end{aligned}
> $$

---

## Principio di induzione

Per dimostrare che $P(m)$ vale $\forall\ m\in\mathbb{N}$:
1. **Base**: dimostro $P(0)$.
2. **Passo induttivo**: assumo $P(m)$ e dimostro $P(m+1)$.

Allora $P(m)$ vale $\forall\ m$.

> [!example] Principio di induzione
> $Q(m):\ 2^m \le (m+1)!$
> - Base $Q(0)$: $2^0=1\le (0+1)!=1$.
> - Passo: assumo $2^m\le (m+1)!$. Allora
>   $$
>   2^{m+1}=2\cdot 2^m \le 2\cdot (m+1)! \le (m+2)(m+1)!=(m+2)!
>   $$

### Induzione forte

Per dimostrare $P(m)$:
- assumo $P(k)$ vero $\forall\ k<m$;
- dimostro $P(m)$.

Allora $P(m)$ vale $\forall\ m$.

> [!note] Utilità
> L'induzione forte serve quando il passo induttivo richiede più casi precedenti, ad esempio per alberi binari e MergeSort.

### Alberi binari

- **Altezza**: lunghezza del cammino più lungo dalla *radice* a una *foglia*.

> [!info] Teorema
> Per ogni albero binario $T$ di altezza $m$, allora:
> $$
> \#\text{foglie}(T)\le 2^m
> $$

**Dimostrazione per induzione** su $m$:
- **Base** $m=0$: l'albero è una sola foglia $\Rightarrow 1\le 2^0=1$.
- **Passo** $(P(m)\to P(m+1))$: sia $T$ di altezza $m+1$. La radice ha due sottoalberi $T'$ e $T''$ di altezze $m',m''\le m$. Allora (se uso *induzione completa*):
  $$
  \#\text{foglie}(T)
  =\#\text{foglie}(T')+\#\text{foglie}(T'')
  \le 2^{m'}+2^{m''}
  \le 2^m+2^m
  =2^{m+1}
  $$

---

## Tempo di esecuzione

Per evitare di calcolarlo ogni volta si prendono le caratteristiche principali dell'algoritmo.

Prendiamo $f,g:\ \mathbb R^+\to\mathbb R^+$ con:
- $f(n)$ la funzione in esame della *complessità* del problema $P$;
- $g(n)$ è la funzione che moltiplicata per la costante $c$, dopo un certo $n$, fa da limite *superiore* o *inferiore* per ogni punto di $f(n)$.

Abbiamo quindi tre tipi di limite:
1. **Limite asintotico superiore** ($O$): $f(n)=O(g(n))$ se esiste $c>0$ tale che $0\le f(n)\le c\cdot g(n)$ per ogni $n\ge n_{0}$.
2. **Limite asintotico inferiore** ($\Omega$): $f(n)=\Omega(g(n))$ se esiste $c>0$ tale che $0\le c\cdot g(n)\le f(n)$ per ogni $n\ge n_{0}$.
3. **Limite asintotico stretto** ($\Theta$): $f(n)=\Theta(g(n))$ se esistono $c_{1}>0$ e $c_{2}>0$ tali che $0\leq c_{1}\cdot g(n)\leq f(n)\leq c_{2}\cdot g(n)$ per ogni $n\geq n_{0}$.

### Metodo del limite

Date $f(n),g(n)>0$:
1. Se $\displaystyle\lim_{n\to\infty}\frac{f(n)}{g(n)}=k>0$ e $k\ne\infty$, allora $f(n)=\Theta(g(n))$.
2. Se $\displaystyle\lim_{n\to\infty}\frac{f(n)}{g(n)}=0$, allora $f(n)=O(g(n))$ e $f(n)\ne\Omega(g(n))$.
3. Se $\displaystyle\lim_{n\to\infty}\frac{f(n)}{g(n)}=\infty$, allora $f(n)=\Omega(g(n))$ e $f(n)\ne O(g(n))$.

**N.B.**: non è valido il contrario; per esempio se $f(n)=\Theta(g(n))$ non è detto che il limite sia $>0$ e $\ne\infty$.

**Osservazioni**:
- Se $f(n)=a_{k}n^k+a_{k-1}n^{k-1}+\dots+a_{1}n+a_{0}=\Theta(n^k)$ allora
  $$
  \lim_{n\to\infty}\frac{f(n)}{n^k}=a_{k}>0.
  $$
- Se $\Theta(n^h)\ne\Theta(n^k)$ con $h\ne k$ allora
  $$
  \lim_{n\to\infty}\frac{n^h}{n^k}=\infty \text{ o } 0.
  $$
- Se $\Theta(a^n)\ne\Theta(b^n)$ con $a\ne b$ e $a,b>0$ allora
  $$
  \lim_{n\to\infty}\frac{a^n}{b^n}=\lim_{n\to\infty}\left(\frac{a}{b}\right)^n=
  \begin{cases}
  0 & a<b,\\
  \infty & a>b.
  \end{cases}
  $$
- Se $\Theta(\log_a n)=\Theta(\log_b n)$ allora
  $$
  \log_a n=(\log_a b)\cdot(\log_b n).
  $$

---

## Complessità dei problemi

> [!info] Complessità
> Dato un problema $P$, la **complessità** di $P$ è la complessità dell'algoritmo *più efficiente* che risolve $P$.

**Limite superiore**: un algoritmo $A$ che risolve $P$ con complessità $O(g(n))$ determina un **limite superiore** $O(g(n))$ per la complessità di $P$.

> [!example] Limite superiore
> Insertion Sort: $O(n^2)$  
> Merge Sort: $O(n\log n)$

**Limite inferiore**: se ogni algoritmo $A$ che risolve $P$ ha complessità $\Omega(g(n))$, allora $P$ ha complessità $\Omega(g(n))$.

> [!example] Limite inferiore
> Ordinamento: $\Omega(g(n))$ — devo almeno leggere gli elementi.

**Limite stretto**: se $P$ è $\Omega(f(n))$ e $O(f(n))$ si dice che $P$ è $\Theta(f(n))$.

---

## Metodo di sostituzione

Può essere usato in alternativa al **Master Theorem**. Ha due fasi:
1. ipotesi di soluzione;
2. verifica che la soluzione è corretta per induzione.

> [!example] Metodo di sostituzione
> $$
> T(n)=\begin{cases}
> 4 & \text{se } n=1,\\
> 2T\left(\frac{n}{2}\right)+6n & \text{se } n>1.
> \end{cases}
> $$
>
> **Ipotesi**: considerando $a,b,c$ opportune costanti, ipotizzo
> $$
> T(n)=an\log_2 n+bn+c.
> $$
> Dimostro per induzione che questa è la soluzione.
> - Caso base ($n=1$):
>   $$
>   T(1)=a\cdot1\cdot\log_2 1+b\cdot1+c=\boxed{b+c=4}.
>   $$
> - Passo induttivo ($n>1$): assumendo che $\forall m<n$, $T(m)=am\log_2 m+bm+c$, voglio dimostrare che vale per $n$:
>   $$
>   \begin{aligned}
>   T(n)&=2T\left(\frac{n}{2}\right)+6n \quad \left(\frac{n}{2}<n,\ \text{uso ip. induttiva}\right)\\
>   &=2\left(a\frac{n}{2}\log_2\frac{n}{2}+b\frac{n}{2}+c\right)+6n\\
>   &=an(\log_2 n-1)+bn+2c+6n\\
>   &=an\log_2 n+(-a+b+6)n+2c.
>   \end{aligned}
>   $$
>   Voglio che valga
>   $$
>   an\log_2 n+bn+c.
>   $$
>   Serve quindi che:
>   $$
>   \begin{aligned}
>   a-b+6&=b & &\Rightarrow a=6,\\
>   2c&=c & &\Rightarrow c=0,\\
>   b+c&=4,\ c=0 & &\Rightarrow b=4.
>   \end{aligned}
>   $$
>
> Soluzione:
> $$
> \boxed{T(n)=6n\log_2 n+4n}\quad\Rightarrow\quad T(n)=\Theta(n\log n).
> $$

---

## Master Theorem

Dato $T(n)$ che rappresenta il **tempo totale** dell'algoritmo dato un input $n$:
$$
T(n)=a\cdot T\left(\frac{n}{b}\right)+f(n),
$$
con $a\geq1$ il numero di sottoproblemi, $\frac{n}{b}$ con $b>1$ la dimensione dei sottoproblemi, e $f(n)$ il costo della parte non ricorsiva.

Confrontando $f(n)$ con $n^{\log_b a}$, si hanno tre casi:
1. $T(n)=\Theta\left(n^{\log_b a}\right)$ se $f(n)=O\left(n^{\log_b a-\epsilon}\right)$ per $\epsilon>0$;
2. $T(n)=\Theta\left(n^{\log_b a}\log n\right)$ se $f(n)=\Theta\left(n^{\log_b a}\right)$;
3. $T(n)=\Theta\left(f(n)\right)$ se $f(n)=\Omega\left(n^{\log_b a+\epsilon}\right)$ per $\epsilon>0$ e vale la *regolarità*: $\exists k$ con $0<k<1$ tale che $f\left(\frac{n}{b}\right)\leq kf(n)$ per ogni $n\geq n_{0}$.

### Utilizzo

Con il *metodo del limite* per il confronto tra $f(n)$ e $n^{\log_b a}$:
- $\displaystyle\lim_{n\to\infty}\frac{f(n)}{n^{\log_b a}}=k>0,\ k\ne\infty \Rightarrow f(n)=\Theta(n^{\log_b a})$ (*caso 2*);
- $\displaystyle\lim_{n\to\infty}\frac{f(n)}{n^{\log_b a}}=0 \Rightarrow f(n)=O(n^{\log_b a})$ e $f(n)\ne\Omega(n^{\log_b a})$ (*caso 1*).
  Infine devo trovare $\epsilon>0$ tale che
  $$
  \lim_{n\to\infty}\frac{f(n)}{n^{\log_b a-\epsilon}}=0\quad\Rightarrow\quad T(n)=\Theta(n^{\log_b a});
  $$
- $\displaystyle\lim_{n\to\infty}\frac{f(n)}{n^{\log_b a}}=\infty \Rightarrow f(n)=\Omega(n^{\log_b a})$ e $f(n)\ne O(n^{\log_b a})$ (*caso 3*).

> [!example] Master Theorem applicato a MergeSort
> $$
> \begin{aligned}
> T(n)&=T\left(\frac{n}{2}\right)+T\left(\frac{n}{2}\right)+a'n+b'\\
> &=2T\left(\frac{n}{2}\right)+\underbrace{a'n+b'}_{f(n)}.
> \end{aligned}
> $$
> Dato che $a=2$ e $b=2$, allora $n^{\log_b a}=n^{\log_2 2}=n^1=n$.
> Quindi
> $$
> \lim_{n\to\infty}\frac{a'n+b'}{n}>0,\ \ne\infty.
> $$
> Sono nel *caso 2* del Master Theorem, quindi
> $$
> T(n)=\Theta(n\log n).
> $$

Nel caso non sia possibile risolvere con il Master Theorem si usa il metodo di sostituzione.

---

## Insertion Sort Ricorsivo

### Pseudocodice

```python
InsertionSort(A, j):
    if j>1:
        InsertionSort(A, j-1)
        Insert(A,j)

Insert(A, j):
    if (j>1) and (A[j-1]>A[j]):
        A[j-1] <-> A[j]
        Insert(A,j-1)
```

### Analisi

- Costo della funzione `Insert`:
  $$
  T^{INS}(j)=c+T^{INS}(j-1)\quad\Rightarrow\quad T^{INS}(j)=\Theta(j)
  $$
- Costo funzione `InsertionSort`:
  $$
  T^{IS}(n)=T^{IS}(n-1)+T^{INS}(n)+c
  $$

Quindi in totale
$$
\boxed{T^{IS}(n)=T^{IS}(n-1)+\Theta(n)=\Theta\left(n^2\right)}
$$

### Duplicazione

Dato `A[1..n]` si dice duplicato:

```
┌─────┬───┬─────┬───┬─────┐
│     │ v │     │ v │     │
└─────┴───┴─────┴───┴─────┘
        i     <     j
```
Dove $i<j$ e `A[i]=A[j]`

==Osservazione==: `dup(A[p..r])=dup(A[p..q])` $\cup$ `dup(A[q+1,r])` $\cup$ `dupCross(A,p,q,r)`

> [!info] Idea
> Per trovare i duplicati, arco-ordino l'array in modo simile al merge sort.
> 
> Metodo `CheckCrossDup(A,p,q,r)` che prende `A[p,q],A[q+1,r]` ordinati e verifica la presenza di duplicati <u>cross</u>, se non ce ne sono ordina `A[p..r]`.

Per contare i duplicati:
$$
|\left\{(i,j)|\ 1\le i<j\le n\ \wedge\ \texttt{A[i]=A[j]}\right\}|
$$

```c
CountDup(A,p,r)
    if p<r
        q= (p+r)/2
        return CountDup(A,p,r)+CountDup(A,q+1,r)+CountCrossDup(A,p,q,r)
    else
        return 0;
```

---

## HeapSort

==Complessità==:
- tempo $\Theta(n\log n)$
- spazio $\Theta(1)$

> [!info] Albero Binario Completo
> 1. Ogni nodo non foglia ha solo due figli
> 2. Ogni cammino radice-foglia ha la stessa lunghezza
> 
> Quindi un albero è **completo** se ha la radice, con due figli e ognuno di essi è radice di un sottoalbero completo della stessa altezza.

==Proposizione==: Un albero completo di altezza $h$ ha un numero di nodi $2^{h+1}-1$.

==Dimostrazione==: Per induzione su $h$; $n(\operatorname{T})=$ numero di nodi dell'albero $\operatorname{T}$.
- Caso base $(h=0)$: $n(\operatorname{T})=1=2^{0+1}-1\quad\checkmark$
- Passo induttivo $(h>0)$: dove $h'=h-1$, quindi:
  $$
  n(\operatorname{T})=n(\operatorname{T}_1)+n(\operatorname{T}_2)+1=2\left(2^{h'+1}-1\right)+1=2(2^h-1)+1=2^{h+1}-1\quad\checkmark
  $$

> [!info] Albero binario quasi completo
> Tutti i livelli sono completi tranne l'ultimo dove le foglie sono solo a sinistra.

> [!info] Heap
> È un albero binario ordinato quasi completo implementato come array.
> 
> Ci sono due tipi di **Heap**:
> - **Max Heap**: dove ogni nodo `A[i]` è $\ge$ dei suoi figli, ma $\le$ dei suoi antenati/parenti
> - **Min Heap**

---

## QuickSort

==Complessità==:
- Caso peggiore: $O(n^2)$
- Caso medio/migliore: $O(n\log n)$

> [!info] Funzionamento
> Come il MergeSort, applica il principio <u>divide et impera</u>:
> - **Partiziona**: sceglie un elemento $x$ detto <u>Pivot</u> in `A[p..r]`, adesso divide l'array in modo che ogni elemento di `A[p:q-1]` sia minore o uguale del pivot, mentre ogni elemento in `A[q+1:r]` è maggiore o uguale al pivot.
> - **Impera**: ordina `A[p:q-1]` e `A[q+1:r]` ricorsivamente
> - **Combina**: Non fa nulla, dato che gli array sono già ordinati, non serve combinarli



---

## Ricerca Binaria
==Pseudocodice==:
```python
Search(A, p, r, k)  # A è un array ordinato
    if p>r
        return 0
    else
        q=(p+r)/2
        if A[q]==k
            return q
        else if A[q]>k
            return Search(A,p,q-1,k)
        else # A[q]<k
            return Search(A,q+1,r,k)
```
==Complessità==:$$T(n)=\Theta(1)+T\left(  \frac{n}{2} \right)$$
$f(n)=\Theta(1)\ =\ n^{\log_{b}a}=n^{\log_{2}1}=n^0=1$
Caso 2 *Master Theorem*$$T(n)=\Theta\left(n^{\log_{b}a}\cdot \log n\right)=\boxed{\Theta(\log n)}$$


---

## Esercizi

- 01/10/2026
- 05/10/2026