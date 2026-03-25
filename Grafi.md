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
### Teorema 1
$$\sum d(v) = 2 \cdot |E|$$
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

Un sottografo *G*'(*V*', *E*') del grafo G(V, E) si dice **indotto** se *E*' contiene tutti gli archi di E che hanno estremi in *V*'.

#### Attraversare un Grafo
Sia G(V, E) un grafo.
*Def*: Un **Percorso** è una sequenza di vertici V$_1$, ... , V$_n$ (non necessariamente distinti) e una sequenza di archi e$_1$, ... , e$_{n-1}$ dove ogni coppia di vertici consecutivi del *percorso* (V$_i$, V$_{i+1}$) è collegata dall'arco e$_i$ 
Un **Percorso** è *chiuso* se gli estremi coincidono.
La *lunghezza* di un **percorso** è il numero di archi attraversati.

Un **Cammino** è un *percorso* con tutti i vertici *distinti*. È una sequenza di vertici V$_1$, ... , V$_n$ *distinti* e una sequenza di archi e$_1$, ... , e$_{n-1}$ dove ogni coppia di vertici consecutivi è collegata dall'arco e$_i$. Per un *percorso* (o *cammino*) i vertici V$_1$ e V$_n$ si chiamano **estremi** del *percorso* (o *cammino*).

Un **Ciclo** è un percorso *chiuso* V$_1$, ... , V$_n$ dove tutti i vertici V$_1$, ... , V$_{n-1}$ sono *distinti* e senza archi ripetuti.

### Teorema 2
Dato un percorso con estrimi V$_1$ e V$_n$ (con V$_1\ne$ V$_n$  quindi *non chiuso*) in G (V, E), esiste un *cammino* con estremi V$_1$ e V$_n$.
Facendo dei **cortocircuiti** nelle ripetizioni dei vertici, si ottiene una *partizione* degli archi in:
1. **Cicli**
2. **Archi** percorsi due volte
3. **Cammino** con estremi V$_1$ e V$_n$

img


### Teorema 3
Un **percorso chiuso** di lunghezza *dispari* contiene almeno un ciclo di lunghezza *dispari*.


### Grafi Connessi
Siano $u,\ v\in V$ per un grafo G(V, E). Si dice che $u$ è **connesso** a $v$ ($u \sim v$) se esiste un cammino di estremi $u$ e $v$. La relazione è:
- **Riflessiva**: $u \sim u$
- **Simmetrica**: $u \sim v \Rightarrow v\sim u$
- **Transitiva**: $u\sim v$, $\ v\sim f\quad\Rightarrow u\sim f$ 
Sia $u\in V$ la classe di equivalenza con rappresentante $u$:
$$[u] = \{v\in V:\ v\sim u\}$$
dove $[u]$ è la componente connessa del grafo che contiene $u$.
Le *classi di equivalenza* si chiamano **componenti connessi** del grafi. Un grafo si dice *connesso* se ha un'unica componente connessa.

## Grafi Bipartiti
Un grafo G(V, E) si dice **bipartito** se V = V$_1 \cup$ V$_2$ con V$_1\cap$ V$_2=\emptyset$, e ogni arco ha un estremo in V$_1$ in V$_2$. Si scrive G(V$_1$, V$_2$, E)


### ISOMORFISMO
Uno stesso grafo si può disegnare nello stesso modo:

IMG


**Definizione**: G(V,E) è *isomorfo*   a G'(V',E') se esiste una biiezione $f:v\rightarrow v$' che conserva le adiacenze:
$$
u,v\in V,\qquad u,v\in E \Leftrightarrow
$$

#### Esercizi
