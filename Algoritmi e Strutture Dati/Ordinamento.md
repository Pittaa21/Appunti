### Insertion Sort
==Idea==:
IMG

**PseudoCodice**:
```
InsertionSort(A)
    m = A.length
    
    for j = 2 to m
        key = A[j]
        i = j-1
        
        while (i>0) && (A[i]>key)
            A[i+1] = A[i]
            i = i-1
        
        A[i+1] = key
```

==Analisi==: Quanto *tempo* costa l'esecuzione di **InsertionSort** $\left(T_{IS}(n)\right)$.

- Il *tempo di esecuzione* è costante per operazioni elementari.
- La *dimensione di un problema*:
    - ordinamento: numero di elementi
    - moltiplicazione: numero di bit dei fattori
$$T_{IS}(n)= c_{0}+c_{1}+nc_{2}+(c_{3}+c_{4}+c_{8})(n-1)+\sum_{j=2}^n(t_{j}+1)c_{5}+\sum_{j=2}^nt_{j}(c_{6}+c_{7})$$
**Problemi**: troppe costanti ignote e dipendenza dalla specifica *istanza* del problema.

==Tempo di Esecuzione==:
- caso migliore $T^{IS}_{min}(n)$
- caso peggiore $T^{IS}_{max}(n)$
- caso medio $T^{IS}_{med}(n)\quad$ *tipicamente coincide con quello peggiore*

**Caso Migliore**: l'array è già ordinato
Quindi$$\begin{align}
 T_{IS}(n) & =c_{0}+c_{1}+nc_{2}+(c_{3}+c_{4}+c_{8})(n-1)+\underbrace{\sum_{j=2}^n(t_{j}+1)c_{5}}_{0}+\underbrace{\sum_{j=2}^nt_{j}(c_{6}+c_{7})}_{0} \\
  & =c_{0}+c_{1}+nc_{2}+(c_{3}+c_{4}+c_{8})(n-1)
\end{align}$$
**Caso Peggiore**: 
$$\begin{align}
 T_{IS}(n) & =c_{0}+c_{1}+nc_{2}+(c_{3}+c_{4}+c_{8})(n-1)+\sum_{j=2}^n\underbrace{(t_{j}+1)}_{j}c_{5}+\sum_{j=2}^n \underbrace{t_{j}}_{j-1}(c_{6}+c_{7})
\end{align}$$
**Caso Medio**: mediamente $t_{j}=\frac{j-1}{2}$



### Merge Sort
**Divide** il problema $P$ in sottoproblemi $P_{1},\dots,P_{n}$ e 
**Impera**, ossia risolve i sottoproblemi in modo *ricorsivo*.
Infine, **Combina** le soluzioni di $P_{1},\dots,P_{n}$ in una soluzione di $P$

==Idea==:
- Si *divide* l'array in due parti uguali
- Si *ordina ricorsivamente* i sottoArray
- Si *fondono* i due sottoArray ordinati

IMG

**PseudoCodice**:
```c
MergeSort(A,p,r)
    if p < r
        q = (p+r)/2
        MergeSort(A,p,q)
        MergeSort(A,q+1,r)
        Merge(A,p,q,r)
        
  
//    pre: A[p,q], A[q+1,r] ordinati 
//    post: A[p..r] ordinato
Merge(A,p,q,r)
    n1 = q-p+1
    n2 = r-q
    for i=1 to n1
        L[i]=A[p+i-1]
    for j=1 to n2
        R[j] = A[q+j]
    // L[n1+1] = R[n2+1] = infinito
    i = j = 1
    for k=p to r
        if L[i]<=R[j]
            A[k] = L[i]
            i++
        else
            A[k] = R[j]
            j++
```
==Dimostrazione==: per ***induzione*** $r-p=l$
- $(l=0)\ r\leq p\rightarrow$ non faccio niente, è giusto $$\begin{align}
A[p..r]= & A[p..p]\quad r=p \\
 & \emptyset\quad r<p
\end{align}$$
- $(l>0)\ r>p\rightarrow$ divido $A[p..r]$ in due parti $l_{1},l_{2}<l$ per *ipotesi induttiva* MergeSort ordina $A[p..q]\ A[q+1..r]$ 

Quindi Merge ha la **precondizione** soddisfatta e quindi produce $A[p..r]$ ordinato.