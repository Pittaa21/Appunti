==Definizione==: Procedura che con semplici istruzione descrive come risolvere un problema

Di ogni algoritmo bisogna sapere:
- Correttezza
- Stabilità
- Complessità

---

## Insertion Sort

> [!info] Idea
> Si costruisce incrementalmente un sottoarray ordinato `A[1..j-1]`.  
> A ogni passo si inserisce `A[i]` nella posizione corretta.

https://upload.wikimedia.org/wikipedia/commons/9/9c/Insertion-sort-example.gif

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
Efficiente per piccole quantità di dati, è uno degli algoritmi più semplice.

- Modello di calcolo: operazioni elementari a costo costante.
- Dimensione del problema: numero di elementi `n`.
- Formula:
  $$
  T^{IS}(n)= c_0+c_1+n c_2+(c_3+c_4+c_8)(n-1)
  +\sum_{j=2}^n (t_j+1)c_5
  +\sum_{j=2}^n t_j(c_6+c_7)
  $$
  dove $t_j$ è il numero di iterazioni del `while` per l’indice `j`.

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

https://commons.wikimedia.org/wiki/File:Merge-sort-example-300px.gif

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
- **Base** $l=0$: `p = r`, `A[p..p]` un solo elemento ⇒ già ordinato.
- **Passo** $l>0\ (p<r)$: si divide `A[p..r]` in due parti. Per ipotesi induttiva, `MergeSort` ordina `A[p..q]` e `A[q+1..r]`. `Merge` opera su i due sottoarray ordinati e, soddisfatta la precondizione, produce `A[p..r]` ordinato.

### Analisi

- spazio occupato in memoria:$$a\cdot n+b$$
$a$ = spazio occupato da un elemento dell'array (`int` 4byte)
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

##### Albero di ricorsione
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

grafico

> [!tip] Interpretazione
> Per $n$ grandi, MergeSort è asintoticamente migliore.  
> Per $n$ piccoli, InsertionSort può essere più veloce per via delle costanti inferiori.
$$
\begin{align}
T^{IS}(n)\ &\approx\ n^2 \\
T^{MS}(n)\ &\approx\ n\log n
\end{align}
$$

### Principio di induzione

Per dimostrare che $P(m)$ vale $\forall\ m\in\mathbb{N}$:

1. **Base**: dimostro $P(0)$.
2. **Passo induttivo**: assumo $P(m)$ e dimostro $P(m+1)$.

Allora $P(m)$ vale $\forall\ m$.

> [!example] Esempio
> $Q(m):\ 2^m \le (m+1)!$
>
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
> L’induzione forte serve quando il passo induttivo richiede più casi precedenti, ad esempio per alberi binari e MergeSort.

### Alberi binari

- **Altezza**: lunghezza del cammino più lungo dalla *radice* a una *foglia*.

> [!info] **Teorema**: per ogni albero binario $T$ di altezza $m$, allora:
  $$
  \#\text{foglie}(T)\le 2^m
  $$

==Dimostrazione per induzione== su $m$:

- **Base** $m=0$: l’albero è una sola foglia ⇒ $1\le 2^0=1$.
- **Passo** $\left(P(m)\to P(m+1)\right)$: sia $T$ di altezza $m+1$. La radice ha due sottoalberi *$T'$* e $T''$ di altezze $m',m''\le m$. Allora (se uso *induzione completa*):$$
  \#\text{foglie}(T)
  =\#\text{foglie}(T')+\#\text{foglie}(T'')
  \le 2^{m'}+2^{m''}
  \le 2^m+2^m
  =2^{m+1}
  $$

##### Tempo Esecuzione
Per evitare di calcolarlo ogni volta si prendono le caratteristiche principali dell'algoritmo.

Prendiamo $f,g:\ \mathbb R^+\to\mathbb R^+$ con:
- $f(n)$ la funzione in esame della *complessità* del problema $P$
- $g(n)$ è la funzione che moltiplicata per la costante $c$, dopo un certo $n$, fa da limite *superiore* o *inferiore* per ogni punto di $f(n)$

Abbiamo quindi due tipi di limite:
1. **Limite asintotico superiore** ($O$), di cui $f(n)=O(g(n))$ se esiste $c>0$ tale che $0\le f(n)\le c\cdot g(n)$ per ogni $n\ge n_{0}$. Quindi $f(n)$ è *O grande* di $g(n)$.
2. **Limite asintotico inferiore** ($\Omega$),  di cui $f(n) = \Omega(g(n))$ se esiste $c>0$ tale che $0\le c\cdot g(n)\le f(n)$ per ogni $n\geq n_{0}$. Quindi $f(n)$ è *omega* di $g(n)$.
3. **Limite asintotico stretto** ($\Theta$), di cui $f(n)=\Theta(g(n))$ se esistono $c_{1}>0$ e $c_{2}>0$ tali che $0\leq c_{1}\cdot g(n)\leq f(n)\leq c_{2}\cdot g(n)$ per ogni $n\geq n_{0}$.

##### Metodo del Limite
Date $f(n),g(n)>0$
1. Se: $$\lim_{ n \to \infty } \frac{f(n)}{g(n)}=k >0 \text{ e }\ne\infty $$allora $f(n)=\Theta(g(n))$

2. Se: $$\lim_{ n \to \infty } \frac{f(n)}{g(n)}=0 $$allora $f(n)=O(g(n))$ e $\ne \Omega(g(n))$

3. Se: $$\lim_{ n \to \infty } \frac{f(n)}{g(n)}=\infty $$allora $f(n)= \Omega(g(n))$ e $\ne O(g(n))$

==N.B.==: non è valido il contrario per esempio se $f(n)=\Theta(g(n))$ non è detto che il limite sia $>0$ e $\ne \infty$.

==Osservazioni==: 
- Se $f(n)=a_{k}n^k+a_{k-1}n^{k-1}+\dots+a_{1}n+a_{0}=\Theta(n^k)$ allora $$\lim_{ n \to \infty } \frac{f(n)}{n^k}=a_{k}>0 $$
- Se $\Theta(n^h)\ne \Theta(n^k)$ con $h\ne k$ allora $$\lim_{ n \to \infty } \frac{n^h}{n^k}=\infty \text{ o }0$$
- Se $\Theta(a^n)\ne \Theta(b^n)$ con $a\ne b$ e $a,b>0$ allora $$\lim_{ n \to \infty } \frac{a^n}{b^n}=\lim_{ n \to \infty } \left(\frac{a}{b}\right)^n=\begin{cases}
&0&a<b \\
&\infty & a>b
\end{cases}$$
- Se $\Theta(\log_{a}n)=\Theta(\log_{b}n)$ allora $$\log_{a}n=(\log_{a}b)\cdot(\log_{b}n)$$

---
### Complessità dei Problemi
> [!info] **Complessità**
> Dato un problema $P$ la **complessità** di $P$ è la complessità dell'algoritmo *più efficiente* che risolve $P$.


**Limite superiore**: Un algoritmo $A$ che risolve $P$ con complessità $O(g(n))$ determina un **limte superiore** $O(g(n))$ per la complessità di $P$. 
> [!example] Esempio
> Insertion Sort $\quad O(n^2)$
> Merge Sort $\quad O(n\log n)$


**Limite inferiore**: Se ogni algoritmo $A$ che risolve $P$ ha complessità $\Omega (g(n))$ allora $P$ ha complessità $\Omega(g(n))$.
> [!example] Esempio
> ordinamento $\quad \Omega(g(n))$ devo almeno leggere gli elementi


**Limite Stretto**: Se $P$ è $\Omega(f(n))$ e $O(f(n))$ si dice che $P$ è $\Theta(f(n))$.

---

### Metodo di Sostituzione
Può essere usato in alternativa al **Master Theorem**. Ha 2 fasi:
1. ipotesi di soluzione
2. verifica che la soluzione è corretta per induzione

> [!example] Esempio 
> $$ \circledast\ T(n)=\begin{cases}
> &4&\text{ se } n=1 \\
> &2T\left( \frac{n}{2} \right)+6n&\text{ se } n>1
> \end{cases}$$

==Ipotesi==: considerando $a,b,c$ opportune costanti, *ipotizzo*:$$T(n)=an\log_{2}n+bn+c$$
Dimostro per induzione che questa è la soluzione di $\circledast$.
- Caso Base $(n=1)$: $$T(1)=a\cdot1\cdot \log_{2}1+b\cdot 1+c=\boxed{b+c=4}$$
- Passo induttivo $(n>1)$: assumendo che $\forall m<n$ $\quad T(m)=am\log_{2}m+bm+c$ voglio dimostrare che vale per $n$: $$\begin{align}
 T(n) & =2T\left( \frac{n}{2} \right)+6n\quad n/2<n, \text{ uso ip. induttiva} \\
  & =2\left(a\frac{n}{2}\log_{2} \frac{n}{2}+b \frac{n}{2}+c\right)+6n \\
   & =an(\log_{2}n-1)+bn+2c+6n \\
    & =an\log_{2}n+(-a+b+6)n+2c \\
     \text{voglio che valga}&=an\log_{2}n+bn+c
\end{align}$$Serve quindi che:$$\begin{align}
 & a-b+6=b & \Rightarrow   a=6 \\
  & 2c=c & \Rightarrow   c=0 \\
   & b+c=4,\ c=0 & \Rightarrow b=4
\end{align}$$Soluzione:$$\boxed{T(n)=6n\log_{2}n+4n}\Rightarrow T(n)=\Theta(n\log n)$$




## Esercizi
- 01/10/2026
- 05/10/2026