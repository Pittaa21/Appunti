### Teoria dei Grafi
**Grafo**: insieme di *nodi* (*vertici*) e di *archi* (*spigoli*). Si rappresenta con G(*V*, *E*) dove *V* è l'insieme finito dei vertici ossia $\{ V_1,\ ...\ ,V_n \}$  e *E* è l'insieme finito degli archi $\{ e_1,\ ...\ ,e_n\}$ . Due vertici si dicono **adiacenti** se esiste un arco di cui loro sono estremi.

![[grafo.svg|center]]

e$_1$ (V$_1$, V$_2$)         inoltre       e$_4\ne$ e$_3$  ma hanno gli stessi *nodi*

Quello rappresentato è un **grafo non-orientato** che a differenza dei **grafi orientati** gli archi sono bidirezionali, altrimenti se monodirezionali al posto di una linea ci sarebbe una freccia.

Ci sono altre due categorie di grafi:
1. **Grafi semplici**: sono grafi che non hanno copie di spigoli *paralleli*, ossia tra due vertici c'è al massimo un arco. Inoltre ogni spigolo ha inizio e fine diversi, non ci sono quindi *cappi* o *paralleli*.
2. **Multigrafi**: sono grafi che non rispettano le caratteristiche dei grafi semplici, quindi possono avere *archi paralleli* e *cappi*.

#### Lista di Adiacenze

d = Grado del vertiche

|       | e$_1$ | e$_2$ | e$_3$ | e$_4$ | d   |
| ----- | ----- | ----- | ----- | ----- | --- |
| V$_1$ | 1     |       | 1     | 1     | 3   |
| V$_2$ | 1     | 1     |       |       | 2   |
| V$_3$ |       | 1     | 1     | 1     | 3   |
$\sum$ d(v) = 3 + 3 + 2 = 8 = 2 $\cdot$ $|$*E*$|$ = 2 $\cdot$ 4

---
**Teorema 1**:     $\sum$ d(v) = 2 $\cdot$ $|$*E*$|$
*Dim*: Ogni arco ha due estremi e quindi contribuisce di 2 alla somma dei gradi


### ISOMORFISMO
Uno stesso grafo si può disegnare nello stesso modo:

IMG


**Definizione**: G(V,E) è *isomorfo*   a G'(V',E') se esiste una biiezione $f:v\rightarrow v$' che conserva le adiacenze:
$$
u,v\in V,\qquad u,v\in E \Leftrightarrow
$$

#### Esercizi
