Sia $\mathbb K$ uno tra $\mathbb R$ e $\mathbb C$. 
Uno **spazio vettoriale** su $\mathbb K$ (che si chiama reale se $\mathbb K=\mathbb R$ e complesso se $\mathbb K=\mathbb C$) è un insieme *non-vuoto* $V$ i cui elementi sono detti **vettori**, su cui sono definite due operazioni:

- **somma** di vettori: $$\begin{align}
V\ \text x\ V\rightarrow V \\
(\underline{v},\underline{w})\rightarrow \underline{v}+\underline{w}
\end{align}$$
- **prodotto** scalare per vettore:$$\begin{align}
\mathbb K\ \text{x }V\rightarrow V \\
(\alpha,\underline{v})\rightarrow \alpha \cdot \underline{v}
\end{align}$$
che soddisfano le proprietà:
1. $\underline{u}+(\underline{v}+\underline{w})=(\underline{u}+\underline{v})+\underline{w}\qquad$ *associativa*
2. $\underline{u}+\underline{v}=\underline{v}+\underline{u}\qquad$ *commutativa*
3. $\alpha \cdot(\beta \cdot \underline{v})=(\alpha \cdot \beta)\cdot \underline{v}$
4. $1\cdot \underline{v}=\underline{v}$
5. $(\alpha+\beta)\cdot \underline{v}=\alpha \cdot \underline{v}+\beta \cdot \underline{v}\qquad$ *distributiva*
6. $\alpha\cdot(\underline{u}+ \underline{v})=\alpha \cdot \underline{u}+\alpha \cdot \underline{v}\qquad$ *distributiva*
7. $\exists\ \underline{o}\in V$ tale che $\underline{v}+\underline{o}=\underline{v}\qquad$ (si può dimostrare che $\underline{o}$ è unico - è l'elemento neutro per +)
8. $\forall \underline{v}\in V$, esiste $\underline{w}\in V$ tale che $\underline{v}+\underline{w}=\underline{o}\qquad$(si può dimostrare che $\underline{w}$ è unico e si indica con $-\underline{v}$ - è l'opposto di $\underline{v}$)

**Proprietà**: $\forall \alpha\in\mathbb K$ e $\forall \underline{v}\in V$ si ha:
 1. $\alpha \cdot \underline{0}=\underline{0}$
 2. $0\cdot \underline{v}=\underline{0}$
 3. $0\cdot \underline{v}=\underline{0}\Leftrightarrow \underline{v}=0$ oppure $\alpha=0$ *legge di cancellazione*<br>(se $\alpha\ne 0$ allora $\underline{v}=^41\cdot \underline{v}=(\alpha^{-1}\cdot \alpha)\cdot$)
 4. $-(\alpha \cdot \underline{v})\dots$

*Esempi*:
1. **Vettori colonna**<br>$V=\mathbb R^n\{\underline{u}=\}$<br>
2. **Spazio Vettoriale** dei **Vettori Riga**<br>$V=\mathbb R_{n}$ o $\mathbb C_{n}$<br>In questi casi<br>$\underline{0}=\begin{pmatrix}0 & \dots & 0\end{pmatrix}$<br>se $\underline{u}=\begin{pmatrix}u_{1} & \dots & u_{n}\end{pmatrix},\ -\underline{u}=\begin{pmatrix}-u_{1} & \dots & -u_{n}\end{pmatrix}$<br>
3. **Spazio vettoriale** delle **Matrici**<br>$V=M_{m,n}(\mathbb K)$<br>$\underline{0}=\emptyset=\begin{pmatrix}0 & \dots & 0 \\ \dots &  & \dots \\ 0 & \dots & 0\end{pmatrix}$<br>se $A=(a_{ij})\in V$ allora $-A=(-a_{ij})\in V$<br>
4. **Spazio Vettoriale** dei **Polinomi** a coefficiente in $\mathbb R$ o $\mathbb C$<br>$V=\mathbb R[x]$ o $\mathbb C[x]$<br>$=\{f(x)=a_{0}+a_{1}x+a_{2}x^2+\dots+a_{n}x^n|ai\in \mathbb K\}$<br>In questi casi<br>$\underline{0}$ è il polinomio nullo $f(x)=0$<br>se $f(x)=a_{0}+a_{1}x+\dots+a_{n}x^n,\ -f(x)=-a_{0}-a_{1}x\dots-a_{n}x^n$<br>
5. **Spazio Vett** dei **Polinomi di Grado** al più $n$<br>$V=\mathbb R_{n}[x]=\{f(x)\in\mathbb[x]\ |\ deg(f(x))\le n\}$<br>$V=\mathbb C_{n}[x]$<br>Osserviamo che le operazioni *somma* e *per* sono ben definite su $V$:<br>se $f(x),g(x)\in\mathbb K_{n}[x]$ allora
    - $deg\left(f(x)+g(x)\right)\le \text{max}\{deg(f(x)),deg(g(x))\}\le n$
    - $\forall \alpha\ne 0,\alpha\in\mathbb K,deg(\alpha \cdot f(x))=deg(f(x))\le n$
    - $deg(0\cdot f(x))=deg(\underline{0})=-\infty\le n$
<br>*Nota*: $deg(f(x))$ vuol dire il grado di $f(x)$ se $f(x)=x^2,deg(f(x))=2$<br>
6. **Spazio Vett** delle **funzioni** da $[a,b]$ in $\mathbb R$<br>Sia $a<b \in\mathbb R$ e sia $V=F([a,b])$ l'insieme di tutte le funzioni $f:[a,b]\rightarrow\mathbb R$.<br>Se $f,g\in F([a,b])$, abbiamo:
    1. $(f+g)(x)=f(x)+g(x)$ 
    2. $(\alpha \cdot f)(x)=\alpha \cdot f(x)$
    3. $\underline{0}$ è la funzione nulla
    4. $(-f)(x)=-\left(f(x)\right)$<br>
7. **Spazio Vett nullo**: $V=\{\underline{0}\}$ è il più piccolo spazio vettoriale.
## Sottospazi Vettoriali
*Definizione*: Sia $V$ uno spazio vettoriale su $\mathbb K$. Un **sottospazio vettoriale** di $V$ è un sottoinsieme $U$ di $V$ tale che:
1. $\underline{0}\in U$
2. $\underline{u_{1}}+\underline{u_{2}}\in U\ \forall \underline{u_{1}},\underline{u_{2}}\in U$ ($U$ è chiuso per la somma)
3. $\alpha \cdot \underline{u}\in U\ \forall \underline{u}\in U,\ \forall \alpha\in\mathbb K$ ($U$ è chiuso per prodotto per scalare)<br>Scriviamo $U\le V$ 

IMG

*Nota*: 
- $U\subseteq V$, $U$ è sottoinsieme di $V$<br>$U\le V$, $U$ è sottospazio di $V$
- se $U\le V$ allora $U$ è spazio vettoriale su $\mathbb K$ con le operazioni che si ottengono restringendo ad $U$ quelle di $V$.

Sia $V$ uno *spazio vettoriale* su $\mathbb K$. Allora:
1. Se $U\le W\le V\Rightarrow U\le V$
2. Se $U_{1}\le V$ e $U_{2}\le V$ allora $U_{1}\cap U_{2}\le V$
3. $\{\underline{0}\}\le V$ **sottospazio nullo**, $V\le V$ ($V$ è sottospazio di se stesso)

*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K$. Siano $U_{1}$ e $U_{2}$ due sottospazi vettoriali di $V$. La **somma** di $U_{1}$ e $U_{2}$ è$$U_{1}+U_{2}=\left\{\underline{u_{1}}+\underline{u_{2}}\ |\ \underline{u_{1}}\in U_{1}\text{ e }\underline{u_{2}}\in U_{2}\right\}$$Se $U_{1}\cap U_{2}=\{\underline{0}\}$ allora scriviamo $U_{1}\oplus U_{2}$ è lo chiamiamo **somma diretta** di $U_{1}$ e $U_{2}$.

*Osservazione*: $U_{1}+U_{2}$ è sottospazio di $V$.

*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K$. Sia $\underline{v}\in V$. L'**insieme dei multipli** di $\underline{v}$ è:$$<\underline{u}\geq\left\{\alpha \cdot \underline{v}\ |\ \alpha\in\mathbb K\right\}$$
#### Proprietà di $<\underline{v}>$

1. $<\underline{v}>$ è un sottospazio di $V$. Infatti:
    1. $\underline{v}\in<\underline{v}>$ quindi $<\underline{v}>\ne\emptyset$
    2. Siano $\underline{u_{1}},\underline{u_{2}}\in<\underline{v}>$ allora $\underline{u_{1}}=\alpha_{1}\cdot \underline{v}$ e $\underline{u_{2}}=\alpha_{2}\cdot \underline{v}$, quindi $\underline{u_{1}}+\underline{u_{2}}=(\alpha_{1}+\alpha_{2})\cdot \underline{v}\in<\underline{v}>$.
    3. Siano $\underline{u}\in<\underline{v}>$ e $\alpha\in\mathbb K$. Allora $\underline{u}=\beta \cdot \underline{v}$ e $\alpha \cdot \underline{u}=(\alpha \cdot \beta)\cdot \underline{v}\in<\underline{v}>$<br>
2. Se $\underline{v}=\underline{0}$ allora $<\underline{v}=<\underline{0}>=\{\underline{0}\}$ cioè $<\underline{0}>$ ha un **unico elemento**: $\underline{0}$<br>
3. Se $\underline{v}\ne \underline{0}$ allora, se $\alpha,\beta\in\mathbb K$, $\alpha \cdot \underline{v}=\beta \cdot \underline{v}\Leftrightarrow\alpha=\beta$<br>Dunque se $\underline{v}\ne \underline{0}$, $<\underline{v}>$ ha tanti elementi quanti sono i numeri in $\mathbb K$ ($\mathbb R$ o $\mathbb C$), cioè **infiniti**.

## Combinazioni Lineari
***Def***: Sia $V$ uno spazio vettoriale su $\mathbb K\in\left\{\mathbb R,\mathbb C\right\}$. La **combinazione lineare** degli $n$ vettori $\underline{v_{1}},\underline{v_{2}},\dots,\underline{v_{n}}$ di $V$ con coefficienti $\alpha_{1},\alpha_{2},\dots,\alpha_{n}\in\mathbb K$ è il vettore:$$\underline{v}=\alpha_{1}\cdot \underline{v_{2}}+\alpha_{2}\cdot \underline{v_{2}}+\dots+\alpha_{n}\cdot \underline{v_{n}}$$
*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K$. Siano $\underline{v_{1}},\underline{v_{2}},\dots,\underline{v_{n}}$ vettori di $V$. Il **sottospazio** di $V$ **generato** da $\underline{v_{1}},\underline{v_{2}},\dots ,\underline{v_{n}}$ è l'insieme di tutte le combinazioni lineari di $\underline{v_{1}},\dots,\underline{v_{n}}$:$$<\underline{v_{1}},\dots,\underline{v_{n}}\geq\left\{\alpha_{1}\cdot \underline{v_{1}}+\dots+\alpha_{n}\cdot \underline{v_{n}}\ |\ \alpha_{1},\dots,\alpha_{n}\in\mathbb K\right\}$$
*Osservazioni*:
1. $<\underline{v_{1}},\dots,\underline{v_{n}}>$ è sottospazio vettoriale di $V$ ed è il più piccolo sottospazio di $V$ che contiene $\underline{v_{1}},\dots,\underline{v_{n}}$
2. L'insieme dei multipli di $\underline{v}\in V$, $<\underline{v}>$, è lo **spazio generato** da $\underline{v}$
3. Se $\underline{v_{1}},\dots,\underline{v_{n}}\in W\le V$ allora $<\underline{v_{1}},\dots,\underline{v_{n}}>\le W$
4. Per convenzione si pone $<\emptyset\ge\{\underline{0}\}$

### Insieme di Generatori
*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K\in\{\mathbb R,\mathbb C\}$. 
Sia $\textit{S}=\{\underline{v_{1}},\dots,\underline{v_{n}}\}$ un insieme di vettori di $V$. Diciamo che $\textit{S}$ è un **insieme di generatori** di $V$ se $<\textit{S}>\ =\ <\underline{v_{1}},\dots,\underline{v_{n}}>\ =V$, cioè se ogni vettore di $V$ si può scrivere come combinazione lineare dei vettori di $\textit{S}$.

*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K\in\{\mathbb R,\mathbb C\}$. L'insieme $\textit{S}=\{\underline{v_{1}},\dots,\underline{v_{n}}\}$ di vettori di $V$ si dice:
- **Linearmente Indipendente** (*L.I.*): se $$\alpha_{1}\cdot \underline{v_{1}}+\dots+\alpha_{n}\cdot \underline{v_{n}}=\underline{0}\Leftrightarrow\alpha_{1}=\dots=\alpha_{n}=0$$
- **Linearmente Dipendente** (*L.D.*): se non è L.I., quindi esistono $\alpha_{1},\dots \alpha_{n}$ non *nulli* tali che$$\alpha_{1}\cdot \underline{v_{1}}+\dots +\alpha_{n}\cdot \underline{v_{n}}=\underline{0}$$
Il termine *dipendente* indica che possiamo scrivere uno dei vettori come combinazione lineare degli altri.
*Esempio*:$$\begin{align}
 & \begin{pmatrix}
 1 \\
 0 \\
 0
 \end{pmatrix}=1\cdot \begin{pmatrix}
 1 \\
 -1 \\
 0
 \end{pmatrix}+1\cdot \begin{pmatrix}
 0 \\
 1 \\
 0
 \end{pmatrix} \\ & 
 \begin{pmatrix}
 1 \\
 0 \\
 0
 \end{pmatrix}\in\ <\begin{pmatrix}
 1 \\
 -1 \\
 0
 \end{pmatrix},\begin{pmatrix}
 0 \\
 1 \\
 0
 \end{pmatrix}>
\end{align}$$
*Nota*: Verranno considerati solo spazi vettoriali **finitamente generati**, cioè esiste un insieme di generatori ==FINITO==.

#### Proprietà di Insiemi L.I.
1. Se $\underline{v}\in V$ allora $\{ \underline{v} \}$ è L.I. $\Leftrightarrow \underline{v}\ne \underline{0}$
2. Se $\textit{S}$ è un insieme *L.I.* e $\textit{U}\subseteq\textit{S}$ allora anche $\textit{U}$ è *L.I.*
3. In un insieme *L.I.* ==non== ci sono **ripetizioni di vettori**. Di conseguenza in un insieme *L.I.* non possono esserci un vettore e un suo multiplo

## Basi di Spazi Vettoriali
*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K\in \{ \mathbb R,\mathbb C \}$. Una ***Base*** di $V$ è un insieme di vettori di $V$ che sia:
1. un insieme di generatori di $V$
2. *L.I.*

*Nota*: uno spazio vettoriale può avere più **basi**.

#### Teorema di Esistenza ed Equipollenza delle Basi
Sia $V$ uno spazio vettoriale su $\mathbb K\in \{ \mathbb R,\mathbb C \}$. Allora:
1. Ogni insieme $\textit{S}$ di generatori di $V$ contiene, almeno, una base $B$ di $V$.
2. Se $B_{1}$ e $B_{2}$ sono due basi di $V$, allora n° di vettori in $B_{1}=$ n° di vettori in $B_{2}$. Quindi il *numero di vettori di una base* è invariante per lo spazio vettoriale $V$, ed è chiamato **dimensione di $V$** e si indica $dim\ V$.

###### Conseguenza del Teorema
Sia $V$ uno spazio vettoriale con $dim\ V=m$. Sia $\textit{S}$ un insieme di generatori di $V$ con $m$ elementi.
Allora $\textit{S}$ è una **base di $V$**.

##### Proprietà delle dimensioni
Sia $V$ uno spazio vettoriale su $\mathbb K$.
1. Se $U\leq V$ allora $dim\ U\leq dim\ V$. Inoltre:
    - $dim\ U=dim\ V\Leftrightarrow U=V$ 
    - $dim\ U=0\Leftrightarrow U=\{ \underline{0} \}$
2. Se $U_{1},U_{2}\leq V$ allora $dim\ (U_{1}+U_{2})=dim\ U_{1}+dim\ U_{2}-dim(U_{1}\cap U_{2})$

*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K\in \{ \mathbb R,\mathbb C \}$. Una ***Base Ordinata*** di $V$ è una base di $V$ in cui l'ordine degli elementi è fissato.

###### Proprietà
Se $B=\{ \underline{v_{1}},\dots,\underline{v_{n}} \}$ è una *base ordinata* di $V$ allora ogni vettore $\underline{v}\in V$ si scrive in ==modo unico== come combinazione lineare dei vettori di $B$.
Cioè esistono **unici** coefficienti $\alpha_{1},\dots,\alpha_{n}\in\mathbb K$ tali che:$$\underline{v}=\alpha_{1}\cdot \underline{v_{1}}+\dots+\alpha_{n}\cdot \underline{v_{n}}$$Il ***vettore delle coordinate*** di $\underline{v}$ rispetto $B$ è$$C_{B}(\underline{v})=\begin{pmatrix}
\alpha_{1} \\
\dots \\
\alpha_{n}
\end{pmatrix}\in\mathbb K^n$$
 n