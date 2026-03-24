Siano $a,b\in\mathbb Z$,   $n\in\mathbb N$,    $n\ne0$ 
Si dice che *a è congruo a* **b** *modulo* **n** se **n** *divide a - b*  

**Proprietà**: $a \equiv b \mod n\ \Leftrightarrow$ il resto della divisione di $a$ è uguale al resto della divisione di $b$ per $n$ 

## Classi di Congruenza
Fissiamo $n\in\mathbb N,\ n\ne0$.
Osserviamo che *essere congruenti modulo* **n**  è una *relazione* tra l'insieme $\mathbb Z$ e se stesso.  Una relazione tra gli insiemi A e B è un sottoinsieme di A x B


Le *relazione di congruenza* ha le seguenti proprietà:
1. **Riflessiva**:  $a \equiv a \mod n\qquad \forall a\in\mathbb Z$
2. **Simmetrica**: Se $a\equiv b \mod n$ allora $b \equiv a \mod n$ 
3. **Transitiva**: Se $a\equiv b \mod n$ e $b\equiv c\mod n$  allora $a\equiv c \mod n$

Una relazione che ha le 3 proprietà è detta **Relazione d'equivalenza**.

4. **Rispetto della Somma**: Se $a_1 \equiv b_1 \mod n$  e  $a_2 \equiv b_2 \mod n$  allora  $a_1+a_2 \equiv b_1 + b_2 \mod n$ 
5. **Rispetto del Prodotto**: Se $a_1 \equiv b_1 \mod n$  e  $a_2 \equiv b_2 \mod n$  allora $a_1 \cdot a_2 \equiv b_1 \cdot b_2 \mod n$ 

---
*Def*: Siano $n \in \mathbb N,\ n\ne0,\ a\in\mathbb Z$
La **Classe di Congruenza di a modulo n** è l'insieme di tutti i numeri interi congrui ad *a modulo n*:
$$
\left[a\right]_n = \{b\in\mathbb Z\text{ tali che }b\equiv a\mod n\}
$$
---
*Nota*:$[a]_n$ è un insieme **infinito** che contiene tutti i numeri che divisi per $n$ danno come resto $a$.

Ogni elemento di $[a]_n$ è detto **Rappresentante** della classe di congruenza di $a$ mod $n$

#### Proprietà
1. $\qquad[a]_n = \{a + K\cdot n\ ,$  con  $K\in\mathbb Z\}$
2. $\qquad[a]_n = [a+K\cdot n]_n$  per ogni  $\large K\in\mathbb Z$
3. $\qquad c\in [a]_n\qquad\Leftrightarrow\qquad [a]_n = [c]_n$
4.    Se $a = q\cdot n+r$ con $0\le r<n$, allora $[a]_n = [r]_n$

*Dimostrazione*:
1. b - a  è multiplo di n$$\begin{aligned} &b\in[a]_n\Leftrightarrow b\equiv a \mod n\\ &\Leftrightarrow n\ |\ (b-a)\Leftrightarrow b-a = K\cdot n \text{ per } K\in\mathbb Z\\&\Leftrightarrow b=a+K\cdot n\end{aligned}$$
2.  Se: $$\begin{aligned}&b\in[a]_n\Rightarrow b= a + K\cdot n\Rightarrow b\in[a+K\cdot n]_n\\&b\in[a+K\cdot n]_n\Rightarrow b\equiv a+K\cdot n \mod n\\&\text{transitiva }\Rightarrow b\equiv a\mod n\\&\Rightarrow b\in[a]_n\end{aligned}$$
Abbiamo dimostrato che $[a]_n \subseteq [a+K\cdot n]_n$  e  $[a]_n \supseteq [a+K\cdot n]_n$  quindi vale l'uguaglianza.
<br>
3. Se $c\in[a]_n$ allora: $$\begin{aligned}&c = a+k\cdot n\quad k\in\mathbb Z\\&\Rightarrow [c]_n = [a+k\cdot n]_n = [a]_n\\&\Rightarrow [c]_n = [a]_n\end{aligned}$$
Visto che $c\in[c]_n$ allora $c\in[a]_n$
<br>
4. $\large a = q\cdot n+r$ $$\begin{aligned}&\Rightarrow r=a-q\cdot n\ \in [a]_n\\&\Rightarrow[r]_n=[a]_n\end{aligned}$$

*Oss*: poniamo $n\in\mathbb N$, $n\ne0$
1. 2 classi di congruenza modulo **n** diverse **NON hanno elementi in comune**.
2. Le classi di congruenza modulo **n** costituiscono unna *partizione* di $\mathbb Z$. Ogni numero intero appartiene ad una e una sola classe di congruenza modulo **n**.

#### Congruenze con Incognite
*Def*: Sia $n\in\mathbb N$, $n\ne0$.  Una **congruenza di modulo n** è un'espressione del tipo$$ a\cdot x\equiv b\mod n\qquad\circledast$$ dove $a,b\in\mathbb Z$.
$x_0\in\mathbb Z$ è una *soluzione* di $\circledast$ se  $a\cdot x_0\equiv b \mod n$.
**NON** tutte le congruenze hanno *soluzioni*.

Esempi:
1. $n=4,\quad 2\cdot x\equiv 3\mod 4$  
**non ha soluzioni** !
Per *assurdo*, $x_0\in\mathbb Z$ è una soluzione. Quindi $2\cdot x_0\equiv 3\mod 4$  ossia $3=2\cdot x_0-4\cdot k$  **Impossibile** 

2. $n=4,\quad 3\cdot x\equiv 2\mod 4$
una *soluzione* è $x_0=2$ e anche $x_1=10$

**Proposizione**: Sia $n\in\mathbb N,\ n\ne0,\ a,b\in\mathbb Z$  e si consideri la congruenza: $a\cdot x\equiv b\mod n\quad\circledast$ 
Se $\circledast$ ha *soluzioni* e $x_0$ è una di queste allora tutti i numeri interi in $[x_0]_n$ sono *soluzioni*. Però non significa che quelle sono **tutte le soluzioni**.

### Teorema 1 (Esistenza di Soluzioni di Congruenze)
Siano $n\in\mathbb N,\ n\ne0,\ a,b\in\mathbb Z$ Allora
$a\cdot x\equiv b\mod n$ ha soluzioni se e solo se MCD($a,n$) divide $b$.
In tal caso una soluzione è $x_0 = \frac b{MCD(a,n)}\cdot \alpha$  con $\large \alpha\in\mathbb Z$ 
con $\alpha \in \mathbb Z$ tale che MCD($a$,$n$) = $\alpha\cdot a + \beta \cdot n$
(e quindi tutti gli interi in $[x_0]_n$ sono soluzioni)
*Dim*: lezione 5

### Teorema 2 (Determinare tutte le soluzioni)
Siano $n\in\mathbb N,\ n\ne0,\ a,b\in\mathbb Z$ e supponiamo che: $$a\cdot x\equiv b \mod n\qquad\circledast$$
ammetta *soluzioni*.
Allora tutte le soluzioni di $\circledast$ sono tutti e soli i numeri interi del tipo:$$x_K = x_0 + K\cdot \frac{n}{MCD(a,n)}\quad \forall K\in\mathbb Z$$
dove $x_0$ è una soluzione *particolare*.

*Oss*: il **Teorema 2** ci dice quali (quante) sono le classi di congruenza modulo $n$ in cui si distribuiscono le *soluzioni*.

Le *soluzioni* di $a\cdot x\equiv b\mod n$  sono:
- $x_0$ (trovata con il **Teorema 1**)
- $x_1 = x_0 + 1 \cdot \frac{n}{MCD(a,n)}$ 
- $x_2 = x_0 + 2 \cdot \frac{n}{MCD(a,n)} = x_0+2\cdot\frac nd$
- $x_d = x_0 + d \cdot \frac nd = x_0 + n\in[x_0]_n$
- $x_{d+1} = x_0 + (d+1) \cdot \frac nd = x_0 + \frac nd + n\in[x_1]_n$

Le *soluzioni* sono **infinite** , ma si ripartiscono in **d = MCD(a, n)**  classi di *convergenza* modulo n $$[x_0]_n\ \cup\ [x_1]_n\ \cup\ ...\ \cup\ [x_{d-1}]_n$$
Esempio
$15\cdot x\equiv 4\mod 20$
$MCD(15,20) = 5$ che non divide $4$   *non ci sono soluzioni*

$2\cdot x\equiv 4\mod 6$
$MCD(2,6) = 2$ che divide $4$    *ci sono soluzioni* per **Teorema 1** e si ripartiscono in 2 classi di congruenza modulo 6 (**Teoreama 2**): $$[x_0]_6\ \cup\ \left[x_0+\frac n{MCD(a,n)}\right]_6$$ cioè$$[x_0]_6\ \cup\ [x_0+3]_6$$
una soluzione di $x_0$ è 2e l'insieme di tutte le soluzioni è:$$[2]_6\ \cup\ [5]_6$$
*Oss*: si considera $a\cdot x\equiv b\mod n\quad\circledast$    e si suppone che $\circledast$ abbia **soluzioni**. Allora $\circledast$ ha le stesse soluzioni di:$$\frac a{MCD(a,n)}\cdot x\equiv \frac b{MCD(a,n)}\ \mod\ \frac n{MCD(a,n)}$$
Inoltre MCD($a_1,\ n_1$)   quindi le soluzioni di $\circledast$ appartengono tutte ad un'**unica** classe di *convergenza* modulo $\frac n{MCD(a,n)}$ 

*Dim*:    moodle lezione 6

*Nota*: $[2]_3 = [2]_6\ \cup\ [5]_6$ 

## Sistemi di Congruenze
Un *sistema di congruenze* è un'espressione del tipo:
$a_1\cdot x \equiv b_1\mod n_1$
$a_2\cdot x \equiv b_2\mod n_2$     $\huge\}$
$a_t\cdot x \equiv b_t\mod n_t$

dove $a_i,\ b_i\in\mathbb Z,\ \ n_i\in\mathbb N,\ \ n_i\ne0$.
$x_0$ è una **soluzione del sistema** se $x_0$ è contemporaneamente soluzione di **ogni** *congruenza del sistema*.

Risolvere un *sistema di congruenze* significa:
1. dire se il sistema ammette *soluzioni*
2. determinare *tutte le soluzioni*

*Oss*:
1. Se una **congruenza** del sistema **NON** ha soluzioni, allora l'intero sistema **NON** ha soluzioni
2. Anche se tutte le congruenze del sistema ammettono soluzioni, il sistema potrebbe **NON** avere soluzioni

*Nota*: Le osservazioni *1* e *2* valgono anche per sistemi di **equazioni lineari** in $\mathbb{Z,\ Q,\ R}$.

Ad esempio: ........


Il **Teorema** seguente dà una condizione *sufficiente* affinchè *particolari* sistemi di congruenze ammettano soluzioni.
#### Teorema Cinese dei Resti
Si considera il sistema di congruenze:
$\quad\quad\quad\ \ \ x\equiv b_1\mod n_2$
$\circledast\ \huge\{$$\qquad x\equiv b_2\mod n_2$
$\quad\quad\quad\ \ \ x\equiv b_t\mod n_t$

dove $b_i\in\mathbb Z$  e  $n_i\in\mathbb N$   $n_i\ne0$        sono a due a due **comprimi**, ossia MCD($n_i,\ n_j$) = 1 per ogni $j\ne 1$ il sistema ammette soluzioni.

*Oss*: se i moduli non sono a 2 a 2 **comprimi** il sistema potrebbe avere comunque *soluzioni*.


### Metodo risolutivo di Newton
*Caso 1*: sistemi con *2* congruenze
*1*$\quad\quad\quad\ \ \ x\equiv b_1\mod n_1$
*2*$\quad\quad\quad\ \ \ x\equiv b_2\mod n_2$

$b_1,\ b_2\in\mathbb Z$,  $n_1,\ n_2\in\mathbb N$,  $n_1\ne0\ne n_2$,  MCD($n_1,\ n_2$) = 1 (**Teorema cinese dei resti** garantisce *soluzioni*)
1. poniamo $x_1 = b_1$  osserviamo che $x_1$ è soluzione di *1*
2. poniamo $x_2 = x_1+K_2\cdot n_1$   dove $K_2\in\mathbb Z$ è tale che $x_2$ sia soluzione di *2*
Un tale $x_2$ è **soluzione del sistema**. Perchè $x_2$ è soluzione di *2* e anche di *1*.

3. 

*Esempio*:
*1*$\quad\quad\quad\ \ \ x\equiv 4\mod 6$
*2*$\quad\quad\quad\ \ \ x\equiv 3\mod 5$

MCD(6, 5) = 1   $\rightarrow$  i moduli sono comprimi. Posso applicare il metodo di Newton.
1. $x_1 = 4$
2. Troviamo $k_2\in\mathbb Z$ tale che $x_2 = 4 + K_2\cdot 6$  soluzione di *2*, cioè $4+6\cdot K_2\equiv 3\mod 5$
$K_2 \equiv -1\mod 5$   e di conseguenza $x_2 = 4 + (-1)\cdot 6 = -2$
3. $[-2]_{6\cdot5} = [-2]_{30} = [28]_{30}$

*Caso 2*: sistemi con *t* congruenze 

con $b_i\in\mathbb Z$,  $n_i\in\mathbb N$,  $n_i\ne0$,  $n_i$ a 2 a 2 comprimi
1. $x_1 = b_1$  è una soluzione di *1*
2. $x_2 = x_1+k_2\cdot n_1$  con $k_2\in\mathbb Z$  scelto in modo che $x_2$ sia soluzione di *2*
3. $x_3 = x_2 + k_3\cdot(n_1\cdot n_2)$  con $k_3\in\mathbb Z$ scelto in modo che $x_3$ sia soluzione di *3*
4. $x_t = x_{t-1}+k_t\cdot(n_1\cdot n_2\ \cdot\ ...\ \cdot\ n_{t-1})$  con $k_t\in\mathbb Z$ scelto in modo che $x_t$ sia soluzione di *t*

Una tale $x_t$ sarà soluzione particolare del sistema e il **Teorema Cinese del Resto** garantisce che tutte le soluzioni sono interi in $$[x_t]_{n_1\cdot n_2\cdot ...\cdot n_t}$$

### Metodo Risolutivo di Lagrange
per sistemi con 2 congruenze
$\quad x_1\equiv b_1\mod n_1$
$\quad x_2\equiv b_2\mod n_2$
con $b_1,\ b_2\in\mathbb Z$,  $n_1,\ n_2\in\mathbb N$,  $n_1\ne0\ne n_2$,  MCD($n_1$, $n_2$) = 1

**Identità di Bezout**: $$ MCD(n_1,n_2)=1=\alpha_1\cdot n_1+\alpha_2\cdot n_2$$Una soluzione del sistema è $$x_0 = \alpha_1\cdot n_1\cdot b_2 + \alpha_2\cdot n_2\cdot b_1$$
Il teorema Cinese dei Resti garantisce che tutte le soluzioni sono interi in$$[x_0]_{n_1\cdot n_2}$$
### Sistemi di Congruenze generici
$\ \ \ \ \ a_1\cdot x \equiv c_1 \mod m_1$
$\huge\{$  $a_2\cdot x \equiv c_2 \mod m_2$
$\ \ \ \ \ a_t\cdot x \equiv c_t \mod m_t$

$a_i,c_i\in\mathbb Z,\ m_i\in\mathbb N, m_i\ne0$
Vogliamo trovare un sistema del tipo:
$\ \ \ \ x\equiv b_1\mod n_1$
$\huge\{$ $x\equiv b_2\mod n_2$
$\ \ \ \ x\equiv b_t\mod n_t$
con i moduli a 2 a 2 *coprimi* (MCD($n_i$, $n_j$) = 1, i $\ne$ j)

**Strategia risolutiva**:
1. calcolo $d_i$ = MCD($a_i$, $m_i$) per ogni $1\le i\le t$ 
	- se $d_i$ non *divide* $c_i$ allora:  $a_i\cdot x\equiv c_i\mod m_i$ *NON HA SOLUZIONI* e quindi anche l'intero sistema non ne ha

	- se $d_i$ *divide* $c_i$ per ogni $i$ allora: sostituiamo ogni congruenza $a_i\cdot x\equiv c_i\mod m_i$   con la congruenza equivalente $$\frac{a_i}{d_i}\cdot x\equiv \frac{c_i}{d_i}\mod \frac{m_i}{d_i}$$Scriviamo $n_i :=\frac{m_i}{d_i}$ e otteniamo un sistema equivalente a quello dato:
		$\ \ \ \ \frac{a_1}{d_1}\cdot x\equiv \frac{c_1}{d_1}\mod n_1$
		$\huge\{$  $...$
		$\ \ \ \ \frac{a_t}{d_t}\cdot\equiv\frac{c_t}{d_t}\mod n_t$
2. Osserviamo che tutte le soluzioni di $$\frac{a_i}{d_i}\cdot x\equiv\frac{c_i}{d_i}\mod n_i\qquad\circledast$$appartengono ad un'unica classe di congruenza modulo $n_i$  Quindi se $b_i$ è una soluzione di $\circledast$ deduciamo che $\circledast$ equivale a:$$x\equiv b_i\mod n_i$$Determiniamo una soluzione perticolare $b_i\in\mathbb Z$ per ogni congruenza $\frac{a_i}{d_i}\cdot x\equiv \frac{c_i}{d_i} \mod n_i$ e di conseguenza troviamo il sistema nella forma che volevamo
3. Se i moduli $n_1,n_2,...,n_t$ sono a 2 a 2 *coprimi* allora possiamo applicare il **Teorema Cinese dei Resti** e i motodi risolutivi di **Newton** e **Lagrange** per risolvere il sistema. Se i moduli *NON* sono a 2 a 2 *coprimi* servono altre tecniche.

### L'insieme di Interi Modulo $n$
*Def*: **L'insieme degli Interi Modulo** $n$, indicato con $\mathbb Z_n$ è l'insieme:$$\mathbb Z_n = \{[0]_n,[1]_n,\ ...\ ,[n-1]_n\}$$ Gli elementi di $\mathbb Z_n$ non sono numeri interi ma *classi di congruenza*.

#### Somma e Prodotto in $\mathbb Z_n$
$[a]_n + [b]_n = [a+b]_n$
$[a]_n\cdot [b]_n = [a\cdot b]_n$

*Nota*: le operazioni sono *ben definite*, ossia non dipendono dai rappresentanti scelti per le classi.

*Esempio*:   $n=4\rightarrow \mathbb Z_4$
$$\begin{aligned}&[2]_4+[3]_4=[5]_4=[1]_4\\\\&[6]_4+[11]_4=[17]_4=[1]_4 \end{aligned}$$
#### Tavole di Somma e Prodotto in $\mathbb Z_n$
- $n=2\rightarrow \mathbb Z_2=\{\ [0]_2,\ [1]_2\ \}$

|    +    | $[0]_2$ | $[1]_2$ |
| :-----: | :-----: | :-----: |
| $[0]_2$ | $[0]_2$ | $[1]_2$ |
| $[1]_2$ | $[1]_2$ | $[0]_2$ |

| $\huge\cdot$ | $[0]_2$ | $[1]_2$ |
| :----------: | :-----: | :-----: |
|   $[0]_2$    | $[0]_2$ | $[0]_2$ |
|   $[1]_2$    | $[0]_2$ | $[1]_2$ |

### Legame con le congruenze
La congruenza $\quad a\cdot x\equiv b\mod n\quad \circledast$  corrisponde all'equazione in $\mathbb Z_n$ $$[a]_n\cdot X=[b]_n\quad \circledast\circledast$$
- Se $x_0\in\mathbb Z$ è soluzione di $\circledast$, allora $[x_0]_n$ è soluzione di $\circledast\circledast$.
- Se $X_0=[x_0]_n\in\mathbb Z_n$ è soluzione di $\circledast\circledast$, allora ogni intero in $X_0=[x_0]_n$ è soluzione di $\circledast$.

Non tutte le equazioni lineari in $\mathbb Z_n$ hanno soluzioni, ma anche possono avere più soluzioni.
Ricordiamo che però il **Teorema Fondamentale dell'algebra** dice che tutte le equazioni lineari in $\mathbb C$ hanno una e una sola soluzione: $ax=b\Rightarrow x= \frac ba$

### Elementi Invertibili in $\mathbb Z_n$
*Def*: sia $n\in\mathbb N,\ n\ne0$.
- Un numero intero $a\in\mathbb Z$ si dice **invertibile modulo** $n$ se la congruenza $a\cdot x\equiv 1\mod n$ *ha soluzione*.
- L'elemento $[a]_n\in\mathbb Z_n$ si dice **invertibile** in $\mathbb Z_n$ se l'equazione  $[a]_n\cdot X=[1]_n$ *ha soluzione*.

*Oss*: 
1. $a\in\mathbb Z$ è *invertibile* mod $n\Leftrightarrow$ MCD($a$, $n$) divide 1 e $\Leftrightarrow$ MCD($a$, $n$) = 1 ($a$ e $n$ sono coprimi)
2. Se $[a]_n\cdot X=[1]_n$  allora $b$ è una soluzione di $a\cdot x\equiv 1\mod n$. Poichè MCD($a$, $n$) = 1, deduciamo che tutte le soluzioni della congruenza appartengono a $[b]_n$. Deduciamo che $[b]_n$ è l'**unica soluzione** di $[a]_n\cdot X=[1]_n$ ed è chiamata *inverso* di $[a]_n$ e si indica con $[a]^{-1}_n$ 

#### Proprietà
1. $[1]_n\in\mathbb Z_n$ è sempre *invertibile* e $[1]^{-1}_n=[1]_n$
2. $[n-1]_n\in\mathbb Z_n$ è sempre *invertibile* e $[n-1]^{-1}_n = [n-1]_n$
3. Se $[a]_n$ è *invertibile* allora anche $[a]_n^{-1}$ è *invertibile* e l'inverso di $[a]^{-1}_n$ è $[a]_n$