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
*Dim*: Ogni arco ha due estremi e quindi contribuisce di 2 alla somma dei gradi.

Un grafo si dice **K-Regolare** (*K*$\in\mathbb N,$ *k* > 0) se ogni suo vertice ha grado *k*. Esempio:
![[kregolare.svg|center]]

Un grafo si dice **completo** se tutti i vertici sono adiacenti, il grafo completo con *n* vertici si indica con K$_n$ 
Esempio:                                                                  K$_4$
![[completo.svg|center]]

In questo tipo di grafi ognuno dei *n* vertici di K$_n$ ha grado *n* - 1.

#### Sottografi e Sottografi Indotti
Dato un grafo G(V, E), un grafo *G'*(*V'*, *E'*) è un **sottografo** di G(V, E) se *V'* $\subseteq$ V  e *E'* $\subseteq$ E. Quindi *G'* può essere ottenuto da G togliendo alcuni vertici e archi. Se si toglie un vertice da V, si devono togliere da R tutti gli archi che lo hanno come estremo.
   G'(V', E')                                G(V, E)
![[kregolare.svg]]                    ![[completo.svg]]

### ISOMORFISMO
Uno stesso grafo si può disegnare nello stesso modo:

IMG


**Definizione**: G(V,E) è *isomorfo*   a G'(V',E') se esiste una biiezione $f:v\rightarrow v$' che conserva le adiacenze:
$$
u,v\in V,\qquad u,v\in E \Leftrightarrow
$$

#### Esercizi
