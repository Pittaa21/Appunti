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
   G'(V', E')&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;G(V, E)
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
3. **Cammino** con estremi V$_1$ e V$_{10}$
![[cammino(1).svg|center|278]]

### Teorema 3
Un **percorso chiuso** di lunghezza *dispari* contiene almeno un ciclo di lunghezza *dispari*.
Lez 2
### Grafi Connessi
Siano $u,\ v\in V$ per un grafo G(V, E). Si dice che $u$ è **connesso** a $v$ ($u \sim v$) se esiste un cammino di estremi $u$ e $v$. La relazione è:
- **Riflessiva**: $u \sim u$
- **Simmetrica**: $u \sim v \Rightarrow v\sim u$
- **Transitiva**: $u\sim v$, $\ v\sim f\quad\Rightarrow u\sim f$ 
Sia $u\in V$ la classe di equivalenza con rappresentante $u$:
$$[u] = \{v\in V:\ v\sim u\}$$
dove $[u]$ è la componente connessa del grafo che contiene $u$.
Le *classi di equivalenza* si chiamano **componenti connessi** del grafi. Un grafo si dice *connesso* se ha un'unica componente connessa.
*Esempio*:

![[conness1.svg]]                                     ![[conness2.svg]]
1 componente (**connesso**)                           un grafo con 2 componenti (**non connesso**)

## Grafi Bipartiti
Un grafo G(V, E) si dice **bipartito** se V = V$_1 \cup$ V$_2$ con V$_1\cap$ V$_2=\emptyset$, e ogni arco ha un estremo in V$_1$ in V$_2$.
Si scrive G(V$_1$, V$_2$, E)
![[bipartito.svg|center]]
Il grafo **bipartito completo** è un grafo G(V$_1$, V$_{2}$, E), ossia *bipartito*, in cui ogni vertice di V$_1$ è adiacente ad ogni vertice di V$_2$. Si indica con $K_{n_{1},n_{2}}$ dove $|V_{1}|=n_{1}$ e $|V_{2}|=n_{2}$
*Esempio*:
$$K_{1,3}$$
![[bipartito(1).svg|77|center]]

### Teorema 4
Un grafo è **bipartito** se e solo se non contiene *cicli dispari*. Quindi è **bipartito** se e solo se i cicli sono *pari*.
*Esempio*: il grafo contiene un *ciclo dispari* quindi non è **bipartito**.
![[bipartito(2).svg|center]]

### Grafo complementare
Sia G(V, E) un grafo. Il grafo **complementare** di G(V, E) è $\bar{\text{G}}(\text{V},\bar{\text{E}})$ che ha lo stesso insieme di vertici di G(V, E) e come insieme di archi $\bar{\text{E}}$, ossia gli archi che **NON** ci sono in E.$$\forall u,v\in V\left[\begin{aligned}
 &\ u \text{ e } v \text{ sono adiacenti } \\
& \quad\quad \text{in }\bar{G}(V,\ \bar{E})
   \end{aligned}\right]\Leftrightarrow\left[\begin{aligned}
   & \ u\text{ e }v\text{ non sono adiacenti }\\
   &\quad\qquad\text{in }G(V,\ E)
   \end{aligned} \right]$$
*Esempio*:
<span>&emsp;&emsp; </span>G(V, E)<span>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span><span>&emsp;&emsp;&emsp;&emsp;&emsp;</span>$\bar{G}(V,\ \bar{E})$<span>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>$G(V,\ E)\cup \bar{G}(V,\ \bar{E})$
![[compl.svg]]<span>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>![[comple.svg]]<span>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>![[compl(1).svg]]


### ISOMORFISMO
Uno stesso grafo si può disegnare nello stesso modo:
![[iso1.svg|270]]<span>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>![[isom 1.svg|141]]
$$\begin{align}
 & E=\left\{\ ab,\ ac,\ ad,\ bd,\ cd,\ de\ \right\} \\
   & \qquad\quad\downarrow\quad\downarrow\quad\ \downarrow\quad\downarrow\quad\downarrow\quad\downarrow \\
  & E'=\left\{12,\ 13,\ 14,\ 24,\ 34,\ 45\right\}
\end{align}$$

*Definizione*: G(V,E) è *isomorfo*   a G'(V',E') se esiste una *biiezione* $f:v\rightarrow v$' che conserva le adiacenze:
$$
u,v\in V,\qquad u,v\in E \Leftrightarrow f(u)f(v)\in E'
$$

##### Sequenza dei gradi
*Definizione*: $d(v)$ è il grado del vertice $v$. Sia G(V, E) un grafo, la **sequenza dei gradi** di G(V, E) è la stringa di gradi dei vertici ordinati dal più grande al più piccolo.

*Esempio*:
![[gradi.svg]]
Sequenza dei gradi: 3, 1, 1, 1.

**CONDIZIONI NECESSARIE** che i grafi $G(V,\ E)$ e $G'(V',\ E')$ sono *isomorfi*.
1. $G$ e $G'$ hanno lo stesso numero di *vertici*
2. $G$ e $G'$ hanno lo stesso numero di *archi*
3. $G$ e $G'$ hanno la stessa *sequenza dei gradi*
4. $G$ e $G'$ devono avere la stessa *struttura* di cicli e componenti (*isomorfi*)

### Teorema 5
I grafi $G(V,\ E)$ e $G'(V',\ E')$ sono *isomorfi* se e solo se i loro grafi complementari $\bar{G}(V,\ \bar{E})$ e $\bar{G}'(V',\ \bar{E}')$ sono *isomorfi*.
*Esempio*:<span>&emsp;&emsp;&emsp;</span>G<span>&emsp;&emsp;&emsp;</span><span>&emsp;&emsp;&emsp;</span><span>&emsp;&emsp;&emsp;</span><span>&emsp;&emsp;&emsp;</span>G'
![[iso.svg]]![[iso2.svg]]
- $G$ e $G'$ hanno lo stesso numero di *vertici* (4)
- $G$ e $G'$ hanno lo stesso numero di *archi* (5)
- $G$ e $G'$ hanno la stessa *sequenza di gradi*
Bisogna guardare i complementari:
<span>&emsp;&emsp;&emsp;&emsp;&emsp;</span>$\bar{G}$<span>&emsp;&emsp;&emsp;&emsp;&emsp;</span><span>&emsp;&emsp;&emsp;&emsp;&emsp;</span><span>&emsp;&emsp;&emsp;&emsp;&emsp;</span>$\bar{G}'$
![[isocompl.svg]]<span>&emsp;&emsp;&emsp;&emsp;&emsp;</span>![[isocompl2.svg]]
$a\leftrightarrow2\qquad b\leftrightarrow 4\qquad c\leftrightarrow 1\qquad d\leftrightarrow3\qquad \checkmark$

**Bipartito cubico**: per esempio $K_{3,3}$ ha lo stesso numero di *vertici*, *archi* e stessa *sequenza di gradi*.

*Nota*: Quando si vuole determinare se due grafi sono **isomorfi**, se un *grafo complementare* è *bipartito* e l'altro no, allora non sono **isomorfi**.

### Arconettività
*Definizione*: Siano $u,v\in V$. Se esiste un cammino con estremi $u$ e $v$, allora $u$ e $v$ sono **connessi**. Se $u$ e $v$ non sono connessi sono **disconnessi.