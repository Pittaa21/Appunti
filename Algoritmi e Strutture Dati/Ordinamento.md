Ecco una nota Obsidian pronta da incollare, con solo il necessario estratto dai PDF.

---
tags:
  - algoritmi
  - strutture-dati
  - ordinamento
  - induzione
aliases:
  - Appunti ASD 29-09-2026
  - Appunti ASD 01-10-2026
---

# Algoritmi e Strutture Dati

## Insertion Sort

> [!info] Idea
> Si costruisce incrementalmente un sottoarray ordinato `A[1..j-1]`.  
> A ogni passo si inserisce `A[j]` nella posizione corretta.

### Pseudocodice

```text
InsertionSort(A)
    m = A.length
    for j = 2 to m
        key = A[j]
        i = j - 1
        while i > 0 && A[i] > key
            A[i + 1] = A[i]
            i = i - 1
        A[i + 1] = key
```

### Analisi

- Modello di calcolo: operazioni elementari a costo costante.
- Dimensione del problema: numero di elementi `n`.
- Formula:
  $$
  T_{IS}(n)= c_0+c_1+n c_2+(c_3+c_4+c_8)(n-1)
  +\sum_{j=2}^n (t_j+1)c_5
  +\sum_{j=2}^n t_j(c_6+c_7)
  $$
  dove `t_j` è il numero di iterazioni del `while` per l’indice `j`.

> [!warning] Problemi
> - Troppe costanti ignote.
> - Dipende dalla specifica istanza del problema.

### Casi

| Caso | Condizione | $t_j$ | Complessità |
|---|---|---|---|
| Migliore | array già ordinato | $0$ | $T_{IS}^{min}(n)=a n+b=\Theta(n)$ |
| Peggiore | array ordinato al contrario | $j-1$ | $T_{IS}^{max}(n)=a n^2+bn+c=\Theta(n^2)$ |
| Medio | mediamente | $\frac{j-1}{2}$ | $\Theta(n^2)$ |

---

## Merge Sort

> [!info] Divide et Impera
> - **Divide**: divide il problema in sottoproblemi.
> - **Impera**: risolve ricorsivamente i sottoproblemi.
> - **Combina**: fonde le soluzioni in una soluzione del problema originale.

### Pseudocodice

```c
MergeSort(A, p, r)
    if p < r
        q = floor((p + r) / 2)
        MergeSort(A, p, q)
        MergeSort(A, q + 1, r)
        Merge(A, p, q, r)
```

```c
Merge(A, p, q, r)
    n1 = q - p + 1
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

> [!note] Pre/Post
> **Pre**: `A[p..q]` e `A[q+1..r]` sono ordinati.  
> **Post**: `A[p..r]` è ordinato.

### Correttezza

- Si dimostra per induzione su $l = r-p$.
- **Base** $l=0$: `p = r`, un solo elemento ⇒ già ordinato.
- **Passo** $l>0$: si divide `A[p..r]` in due parti. Per ipotesi induttiva, `MergeSort` ordina `A[p..q]` e `A[q+1..r]`.  
  `Merge` soddisfa la precondizione e produce `A[p..r]` ordinato.

### Analisi

- `Merge` costa linearmente: $am+b$.
- Ricorrenza:
  $$
  T^{MS}(m)=
  \begin{cases}
  c_0 & m \le 1\\[4pt]
  T^{MS}\!\left(\left\lfloor \frac{m}{2}\right\rfloor\right)
  +T^{MS}\!\left(\left\lceil \frac{m}{2}\right\rceil\right)
  +am+b & m>1
  \end{cases}
  $$

- Albero di ricorsione:
  - altezza: $h=\log_2 m$
  - costo al livello $j$: $am+2^j b$
  - foglie: $m c_0$

$$
\begin{aligned}
T^{MS}(m)
&= \sum_{j=0}^{h-1}(am+2^j b)+m c_0 \\
&= am\log_2 m+(m-1)b+m c_0 \\
&= \Theta(m\log m)
\end{aligned}
$$

### Confronto Insertion Sort vs Merge Sort

| $n$ | $T_{IS}(n)\sim n^2$ | $T_{MS}(n)\sim n\log_2 n$ |
|---:|---:|---:|
| $10$ | $0{,}1\ \mu s$ | $0{,}033\ \mu s$ |
| $1000$ | $1\ ms$ | $10\ \mu s$ |
| $10^6$ | $17\ min$ | $20\ ms$ |
| $10^9$ | $70\ anni$ | $30\ sec$ |

> [!tip] Interpretazione
> Per $n$ grandi, MergeSort è asintoticamente migliore.  
> Per $n$ piccoli, InsertionSort può essere più veloce per via delle costanti inferiori.

---

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
Analisi mergeSort
spazio occupato in memoria:$$a\cdot n+b$$
$a$ = spazio occupato da un elemento dell'array (`int` 4byte)
$n$ = numero di elementi dell'array
$b$ = spazio occupato dagli *elementi di controllo* (`if`, `for`)

Contesto
$f,g:\ \mathbb R\to\mathbb R$




## Esercizi
- pdf 01/10/2026
- 05/10/2026