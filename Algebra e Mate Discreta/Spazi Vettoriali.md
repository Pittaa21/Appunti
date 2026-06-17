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
1. **Vettori colonna**<br>$V=\mathbb R^n\left\{\underline{u}=\begin{pmatrix}u_{1} \\ \dots \\ u_{n}\end{pmatrix}\ |\ u_{i}\in\mathbb R\right\}$<br>$V=\mathbb C^n$<br>
2. **Spazio Vettoriale** dei **Vettori Riga**<br>$V=\mathbb R_{n}$ o $\mathbb C_{n}$<br>In questi casi<br>$\underline{0}=\begin{pmatrix}0 & \dots & 0\end{pmatrix}$<br>se $\underline{u}=\begin{pmatrix}u_{1} & \dots & u_{n}\end{pmatrix},\ -\underline{u}=\begin{pmatrix}-u_{1} & \dots & -u_{n}\end{pmatrix}$<br>
3. **Spazio vettoriale** delle **Matrici**<br>$V=M_{m,n}(\mathbb K)$<br>$\underline{0}=\emptyset=\begin{pmatrix}0 & \dots & 0 \\ \dots &  & \dots \\ 0 & \dots & 0\end{pmatrix}$<br>se $A=(a_{ij})\in V$ allora $-A=(-a_{ij})\in V$<br>
4. **Spazio Vettoriale** dei **Polinomi** a coefficiente in $\mathbb R$ o $\mathbb C$<br>$V=\mathbb R[x]$ o $\mathbb C[x]$<br>$=\left\{f(x)=a_{0}+a_{1}x+a_{2}x^2+\dots+a_{n}x^n|ai\in \mathbb K\right\}$<br>In questi casi<br>$\underline{0}$ è il polinomio nullo $f(x)=0$<br>se $f(x)=a_{0}+a_{1}x+\dots+a_{n}x^n,\ -f(x)=-a_{0}-a_{1}x\dots-a_{n}x^n$<br>
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
***Def***: Sia $V$ uno spazio vettoriale su $\mathbb K\in\left\{\mathbb R,\mathbb C\right\}$. La ***combinazione lineare*** degli $n$ vettori $\underline{v_{1}},\underline{v_{2}},\dots,\underline{v_{n}}$ di $V$ con coefficienti $\alpha_{1},\alpha_{2},\dots,\alpha_{n}\in\mathbb K$ è il vettore:$$\underline{v}=\alpha_{1}\cdot \underline{v_{2}}+\alpha_{2}\cdot \underline{v_{2}}+\dots+\alpha_{n}\cdot \underline{v_{n}}$$
*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K$. Siano $\underline{v_{1}},\underline{v_{2}},\dots,\underline{v_{n}}$ vettori di $V$. Il **sottospazio** di $V$ **generato** da $\underline{v_{1}},\underline{v_{2}},\dots ,\underline{v_{n}}$ è l'insieme di tutte le combinazioni lineari di $\underline{v_{1}},\dots,\underline{v_{n}}$:$$<\underline{v_{1}},\dots,\underline{v_{n}}>\ =\left\{\alpha_{1}\cdot \underline{v_{1}}+\dots+\alpha_{n}\cdot \underline{v_{n}}\ |\ \alpha_{1},\dots,\alpha_{n}\in\mathbb K\right\}$$
*Osservazioni*:
1. $<\underline{v_{1}},\dots,\underline{v_{n}}>$ è sottospazio vettoriale di $V$ ed è il più piccolo sottospazio di $V$ che contiene $\underline{v_{1}},\dots,\underline{v_{n}}$
2. L'insieme dei multipli di $\underline{v}\in V$, $<\underline{v}>$, è lo **spazio generato** da $\underline{v}$
3. Se $\underline{v_{1}},\dots,\underline{v_{n}}\in W\le V$ allora $<\underline{v_{1}},\dots,\underline{v_{n}}>\le W$
4. Per convenzione si pone $<\emptyset\ge\{\underline{0}\}$

### Insieme di Generatori
*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K\in\{\mathbb R,\mathbb C\}$. 
Sia $\textit{S}=\{\underline{v_{1}},\dots,\underline{v_{n}}\}$ un insieme di vettori di $V$. Diciamo che $\textit{S}$ è un ***insieme di generatori*** di $V$ se $<\textit{S}>\ =\ <\underline{v_{1}},\dots,\underline{v_{n}}>\ =V$, cioè se ogni vettore di $V$ si può scrivere come combinazione lineare dei vettori di $\textit{S}$.

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
 
## Spazi Vettoriali associati a Matrici
Sia $A\in M_{m,n}(\mathbb K)\quad\mathbb K\in \{ \mathbb R,\mathbb C \}$.

1. **Lo spazio delle colonne di $A$**
    È il sottospazio di $\mathbb C^m$ generato dalle colonne di $A$:$$C(A)= <\underline{c_{1}},\dots,\underline{c_{n}}>\ \leq\mathbb C^m$$Per trovare una *Base* di $C(A)$ bisogna:
    1. trovare una *forma ridotta* $u$ di $A$.
    2. $dim\left(C(A)\right)=rk\ A$ (rango di $A$) $=n$° colonne dominanti di $u$.<br>Una *base* di $C(A)$ è data dalle colonne di $A$ che hanno posizione corrispondente alle *colonne dominanti* di $u$. $C(A)\neq C(u)$<br>
2. **Lo spazio delle righe di $A$**
    È il sottospazio di $\mathbb C^n$ generato dalle *H-trasposte* delle righe di $A$. $$\begin{align}
     & R(A)= <\underline{\overline{r_{1}^T}}, \dots, \underline{\overline{r_{m}^T}}>\ \leq\mathbb C^n \\
     & R(A)=C(A^H)
    \end{align}
    $$Per trovare una *base* di $R(A)$ bisogna:
    1. trovare una *forma ridotta* $u$ di $A$.
    2. $R(A)=R(u)$. Una *base* di $R(A)$ è data dalle *H-trasposte* delle righe non-nulle di $u$.

3. **Lo spazio nullo di $A$**
    $$N(A)=\left\{ \underline{v}\in\mathbb C^n\ |\ A\cdot \underline{v}=\underline{0} \right\}\leq\mathbb C^n$$
    $N(A)$ è quindi l'insieme delle soluzioni del sistema lineare $A\cdot \underline{x}=\underline{0}$. È, inoltre uno spazio vettoriale e $\underline{0}\in N(A)$.
    ***Proprietà***: $dim\ (N(A))=dim\mathbb\ C^n-rk(A)$
    Per trovare una *base* di $N(A)$ bisogna:
    1. trovare una *forma ridotta* $u$ di $A$
    2. osservo che $N(A)=N(u)$ e $dim\ (N(A))=n$° colonne di $u-n$° colonne *dominanti* di $u=n$° colonne *libere* di $u$.
        Per trovare la base basta risolvere il sistema $u\cdot \underline{x}=\underline{0}$.
        Se tutte le colonne di $u$ sono *dominanti*, allora $$N(A)=\{ \underline{0} \},\ dim\ (N(A))=0,\ B=\emptyset$$

## Applicazioni Lineari
*Def*: Un'***Applicazione Lineare*** (o *trasformazione lineare*) è una funzione $f:\ V\to W$ tale che:
- $V$ e $W$ sono *spazi vettoriali* definiti sullo stesso $\mathbb K$.
- $f$ conserva la **somma**: $f(\underline{v_{1}}+\underline{v_{2}})=f(\underline{v_{1}})+f(\underline{v_{2}})\ \forall \underline{v_{1}},\underline{v_{2}}\in V$.
- $f$ conserva il **prodotto scalare**: $f(\alpha \cdot \underline{v})=\alpha \cdot f(\underline{v})\ \forall \underline{v}\in V,\alpha\in\mathbb K$.

#### Proprietà Applicazioni Lineari
Sia $f:\ V\to W$ un'*applicazione lineare*.
1. $f(\underline{0}_{v})=\underline{0}_{w}$
2. Se $g:\ W\to Z$ è un'*applicazione lineare*, allora $g$ o $f:\ V\xrightarrow{f}W\xrightarrow{g}Z$ è *applicazione lineare* .

Sia $f:\ V\to W$ un'*applicazione lineare*.
- Lo **spazio nullo** di $f$ è $N(f)=\{ \underline{v}\in V\ |\ f(\underline{v}) =\underline{0}_{w} \}\subseteq V$
- Lo **spazio immagine** di $f$ è $\text{Im}(f)=\{ \underline{w}\in W\ |\ \underline{w}=f(\underline{v})\text{ per }\underline{v}\in V\}\subseteq W$

##### Proprietà
Sia $f:\ V\to W$ un'*applicazione lineare*.

1. $N(f)$ è un *sottospazio vettoriale* di $V$ e $f$ è iniettiva se e solo se $N(f)=\{ \underline{0}_{V} \}\Leftrightarrow dim\ N(f)=0$.
    $f$ è **iniettiva** se dati $\underline{v_{1}},\underline{v_{2}}\in V,\ \underline{v_{1}}\neq \underline{v_{2}}$ si ha $f(\underline{v_{1}})\neq f(\underline{v_{2}})$<br>
2. $\text{Im}(f)$ è un *sottospazio vettoriale* di $W$.
    $f$ è **suriettiva** se e solo se $\text{Im}(f)=W\Leftrightarrow dim\ (\text{Im}(f))=dim\ (W)$<br>
3. $f$ è **isomorfo** (*iniettiva* e *suriettiva*) se e solo se $N(f)=\{ \underline{0}_{v} \}$ e $\text{Im}(f)=W$.

#### Teorema di Nullità + Rango
Sia $f:\ V\to W$ un'*applicazione lineare*. Allora: $$dim\ (V)=dim\ (N(f))+dim\ (\text{Im}(f))$$
## Applicazioni Lineari e Matrici
*Def*: Sia $A\in M_{m,n}(\mathbb K)$ una matrice. L'*applicazione lineare* **indotta** da $A$ è$$\begin{align}
f_{A}:\ \mathbb K^n\to\mathbb K^m \\
\underline{v}\to f(\underline{v})=A\cdot \underline{v}
\end{align}$$
*Nota*: $f_{A}$ è *applicazione lineare*.

*Osservazioni*:
- $N(f_{A})=\{ \underline{v}\in\mathbb K^n\ |\ f_{A}(\underline{v})=\underline{0} \}=N(A)$ **spazio nullo** di $A$. 
- $\text{Im}(f_{A})=\{ \underline{w}\in\mathbb K^m\ |\ \underline{w}=f_{A}(\underline{v})\text{ per }\underline{v}\in\mathbb K^n \}=C(A)$ **spazio delle colonne** di $A$.

Il **Teorema di Nullità + Rango** ci dice che:$$\begin{align}
 & dim(\mathbb K^n)=dim\ N(f_{A})+dim\ \text{Im}(f_{A}) \\
 & n=dim\ N(A)+ \left[\ dim\ C(A)=rk(A)\ \right] \\
\end{align}$$Da cui si ricava la formula:$$dim\ N(A)=n-rk(A)$$
*Def*: Sia $f:\ V\to W$ un'*applicazione lineare*. Siano $B=\{ \underline{v_{1}},\dots,\underline{v_{n}} \}$ una *base ordinata* di $V$ e $D=\{ \underline{w_{1}},\dots,\underline{w_{n}} \}$ una *base ordinata* di $W$.
![[baseOrd.svg|center|290]]
La ***matrice associata*** a $f$ rispetto alle basi $B$ e $D$ è la matrice $A\in M_{m,n}(\mathbb K)$ tale che:$$f_{A}\cdot C_{B}=C_{D}\cdot f$$![[matAsso.svg|center|650]]
cioè: $$A\cdot C_{B}(\underline{v})=C_{D}(f(\underline{v}))\quad\forall \underline{v}\in V$$
*Nota*: una tale $A$ esiste sempre.

##### Strategia per costruire $A$
$A$ è la **matrice** che ha come *colonne*:$$C_{D}(f(\underline{v_{1}})),\dots,C_{D}(f(\underline{v_{n}}))$$
*Osservazione*: Se $f:\ \mathbb K^n\to\mathbb K^m$ e 
$B=\epsilon_{n}=\{ \underline{e_{1}},\dots \underline{e_{n}} \}$ **base canonica** di $\mathbb K^n$.
$D=\epsilon_{m}=\{ \underline{e_{1}},\dots \underline{e_{m}} \}$ **base canonica** di $\mathbb K^m$.
allora $\forall \underline{v}\in V,\ C_{B}(\underline{v})=\underline{v}\quad C_{D}(f(\underline{v}))=f(\underline{v})$

quindi se $A$ è *matrice associata* a $f$ rispetto alle **basi canoniche** allora:$$\begin{align}
 & A\cdot \underline{v}=f(\underline{v}) \\
  & f_{A}(\underline{v})
\end{align}$$cioè $f_{A}=f$.


*Nota*: In generale se $A$ è *matrice associata* a $f$ rispetto alle basi $B$ e $D$ allora: $$N(A)\neq N(f)\text{ e }C(A)\neq\text{Im}(f)$$Ma$$dim(N(A))=dim(N(f))\text{ e }dim(C(A))=dim(\text{Im}(f))$$

*Osservazione*: Siano $f:\ V\to W$ e $g:\ W\to Z$ *applicazioni lineari* e
- $B$ **base ordinata** di $V$
- $D$ **base ordinata** di $W$
- $F$ **base ordinata** di $Z$

Se $A_{1}$ è la *matrice associata* a $f$ rispetto a $B$ e $D$, $A_{2}$ è la *matrice associata* a $g$ rispetto a $D$ e $F$ allora:$$A_{2}\cdot A_{1}$$è la *matrice associata* a $g\cdot f:\ V\xrightarrow{f}W\xrightarrow{g}Z$ rispetto alle basi $B$ e $F$.


###### Matrice di Passaggio di Base
*Def*: Sia $V$ uno *spazio vettoriale* su $\mathbb K\in \{ \mathbb R,\mathbb C \}$, con $dim\ V=n$. Siano $B_{1}$ e $B_{2}$ due basi (ordinate) di $V$.
La ***Matrice di Passaggio di Base*** da $B_{1}$ a $B_{2}$, indicata $\quad M_{B_{2}\leftarrow B_{1}}\quad$ è la *matrice associata* all'applicazione identica $$id_{V}:\ V\to V\quad id_{V}(v)=v$$
Cioè se $B_{1}=\{ \underline{v_{1}},\dots,\underline{v_{n}} \}$ allora $M_{B_{2}\leftarrow B_{1}}(C_{B_{2}}(\underline{v_{1}}),\dots,C_{B_{2}}(\underline{v_{n}}))\in M_{n}(\mathbb K)$.

***Proprietà***:
1. $M_{B_{2}\leftarrow B_{1}}\in M_{n}(\mathbb K)$ è *matrice quadrata* di ordine $n=dim\ V$.
2. Se $B_{1}=B_{2}$ allora $M_{B_{2}\leftarrow B_{1}}=\mathbb 1_{n}$
3. $M_{B_{2}\leftarrow B_{1}}$ è sempre *invertibile* e $$\left(M_{B_{2}\leftarrow B_{1}}\right)^{-1}=M_{B_{1}\leftarrow B_{2}}$$
4. Se $V=\mathbb K^n,\ B=\{ \underline{v_{1}},\dots,\underline{v_{n}} \}$ **base ordinata**, $\epsilon_{n}$ **base cononica**.$$M_{\epsilon_{n}\leftarrow B}=\Bigl(\underline{v_{1}},\dots,\underline{v_{n}}\Bigr)$$

## Interpretazione Geometrica di $\mathbb R^2$
###### Algebra
$\mathbb R^2=\left\{ \binom ab:a,b\in\mathbb R \right\}$
coordinate di vettori rispetto alla base cononica $\epsilon_{2}$.

###### Geometria
$\mathbb R^2$ il piano cartesiano di coordinate dei punti $P(a,b)$. 


## Norme di Vettori
*Def*: Sia $V$ uno spazio vettoriale su $\mathbb K\in \{ \mathbb R,\mathbb C \}$. Una ***norma*** per $V$ è una funzione$$\|\cdot\|:\ V\to\mathbb R\geq0$$tale che:
1. $\|\underline{v}\|>=0\quad\forall \underline{v}\in V,\ \underline{v}\neq \underline{0}$ e $\|\underline{0}\|=0$
2. $\|\alpha \cdot \underline{v}\|=|\alpha|\cdot\|\underline{v}\|\quad\forall \alpha\in\mathbb K,\forall \underline{v}\in V$
3. $\|\underline{v}+\underline{w}\|\leq\|\underline{v}\|+\|\underline{w}\|\quad \forall \underline{v},\underline{w}\in V$ (**disuguaglianza triangolare**)

#### Esempi di Norme per $V=\mathbb K^m$ con $\mathbb K\in \{ \mathbb R,\mathbb C \}$
$$\|\cdot\|:\ \mathbb K^m\to\mathbb R\geq{0}$$
1. **Norma Euclidea** $||\cdot||_{2}$
    in $\mathbb R^2$ "misura la lunghezza di un vettore".
    $\underline{v}=\binom ab\to P(a,b)$
    $\|\underline{v}\|_{2}=\sqrt{a^2+b^2}$
    La ***Norma Euclidea*** è data da:$$\|\underline{v}\|_{2}=\sqrt{\underline{v}^h\cdot \underline{v}}$$cioè$$\left\|\begin{pmatrix}
    v_{1} \\
    \dots \\
    v_{m}
    \end{pmatrix}\right\|=\sqrt{ |v_{1}|^2+\dots+|v_{m}|^2 }\in\mathbb R\geq_{0}$$
    *Nota*: va considerato $\underline{v}^H$ invece di $\underline{v}^T$ affinchè si abbia sempre $\|\underline{v}\|_{2}\in\mathbb R\geq0$.<br>
2. **Norma Taxi-Driver** o **Manhattan** $\|\cdot\|_{1}$
    in $\mathbb R^2$, "conta i passi di lunghezza 1 per andare da $0$ a $P$ muovendosi solo in orizzontake o verticale".
    La **norma** è data da:$$\left\|\begin{pmatrix}
    v_{1} \\
    \dots \\
    v_{m}
    \end{pmatrix}\right\|_{1}=|v_{1}|+\dots+|v_{m}|$$
3. **Norma "Infinito"**:
    In $\mathbb R^2$, "una volta stabilito se è maggiore il numero di passi orizzontali o verticali, mi dà questo numero".
    La **Norma Infinito** è data da:$$\left\|\begin{pmatrix}
    v_{1} \\
    \dots \\
    v_{m}
    \end{pmatrix}\right\|=\text{max }\{ |v_{1}|,\dots,|v_{m}| \}$$
    *Osservazione*: Sia $\underline{v}\in\mathbb K^m$, allora$$\|\underline{v}\|_{\infty}\leq\|\underline{v}\|_{2}\leq\|\underline{v}\|_{1}$$
    in$\mathbb R^2$. D'ora in poi, ci si concentra sulla **Norma Euclidea**.


##### Normalizzazione
*Def*: Sia $\underline{v}\in\mathbb K^n,\ \underline{v}\neq \underline{0}$. ***Normalizzare*** $\underline{v}$ significa considerare l'==unico== multiplo positivo di $\underline{v}$ con norma euclidea uguale a 1:$$\underline{v}'=\frac{1}{\|\underline{v}\|_{2}}\cdot \underline{v}$$

### Il Coseno dell'Angolo tra vettori di $\mathbb K^m$
In $\mathbb R^2$. 
$\underline{v},\underline{w}\in\mathbb R^2,\ \underline{v}\neq{0}\neq \underline{w},\ \underline{v}\neq \underline{w}$.
![[graph.svg|center|334]]

$\underline{v}$ e $\underline{w}$ individuano un unico angolo $\alpha<360°$, andando da $\underline{v}$ a $\underline{w}$. L'angolo non dipende dal sistema di riferimento.

Calcolo il $\cos(\alpha)$:$$\cos(\alpha)=\frac{\underline{v}^H\cdot \underline{w}}{\|\underline{v}\|_{2}\cdot\|\underline{w}\|_{2}}$$
##### Proprietà
Siano $\underline{v},\underline{w}\in\mathbb K^m,\ \underline{v}\neq \underline{0}\neq \underline{w}$.
1. Se $\mathbb K=\mathbb R,\ \alpha$ è l'angolo compreso tra $\underline{v}$ e $\underline{w}$ e $\beta$ è l'angolo compreso tra $\underline{w}$ e $\underline{v}$ allora:$$\cos(\alpha)=\cos(\beta)$$
2. $\cos(\alpha)=0\Leftrightarrow\underline{v}^H\cdot \underline{w}=\underline{0}$

## Vettori Ortogonali e Ortonormali
*Def*: Il **Prodotto interno standard** (o *scalare*) di $\mathbb K^m$ è:$$\begin{align}
 & (\cdot|\cdot):\ \mathbb K^m\text{ x }\mathbb K^m\to\mathbb K \\
  & (\underline{v}|\underline{w})=\underline{v}^H\cdot \underline{w}
\end{align}$$
##### Proprietà
1. $(\underline{v}|\underline{0})=(\underline{0}|\underline{v})=0\quad\forall \underline{v}\in\mathbb K^m$<br>
2. $(\underline{v}|\underline{v})=\underline{v}^H\cdot \underline{v}=\|\underline{v}\|_{2}^2\in\mathbb R\geq0\quad\forall \underline{v}\in\mathbb K^m$<br>
3. $(\alpha \underline{v}|\beta \underline{w})=(\overline \alpha \cdot v_{1}\ \dots\ \overline \alpha \cdot v_{m})\cdot \begin{pmatrix}\beta \cdot w_{1} \\ \dots \\ \beta \cdot w_{m}\end{pmatrix}=\overline \alpha \cdot \beta \cdot(\underline{v}|\underline{w})$
    Se $\alpha,\beta\neq0$ allora $(\alpha \cdot \underline{v}|\beta \cdot \underline{w})=0\Leftrightarrow (\underline{v}|\underline{w})=0$

*Def*: Sia $V\leq\mathbb K^m,\ \mathbb K\in \{ \mathbb R,\mathbb C \}$. Due vettori $\underline{v},\underline{w}\in V$ si dicono ***ortogonali***, e si scrive $\underline{v}\perp \underline{w}$ se $(\underline{v}|\underline{w})=0$.

*Nota*: Se $(\underline{v}|\underline{w})=0$ allora anche $(\underline{w}|\underline{v})=0$.

*Osservazioni*:
1. $\underline{0}$ è ortogonale ad ogni vettore $\underline{v}\in\mathbb K^m$
2. Se $\underline{v}\neq \underline{0}-\underline{w}$ e $\alpha$ è l'angolo compreso tra $\underline{v}$ e $\underline{w}$ allora: $$\underline{v}\perp \underline{w}\Leftrightarrow(\underline{v}|\underline{w})=0\Leftrightarrow\cos(\alpha)=0$$
*Def*: Un insieme $S=\{ \underline{v_{1}},\dots \underline{v_{t}} \}$ di vettori di $V\leq\mathbb K^m$ si dice ***Insieme Ortogonale***, se i suoi vettori sono a due a due **ortogonali**, ossia $\underline{v_{i}}\perp \underline{v_{j}}\ \forall i\neq j$, $(\underline{v_i}|\underline{v_{j}})=0\ \forall i\neq j$.
Una ***Base Ortogonale*** di $V$ è una base che è anche **insieme ortogonale**.

*Def*: Un insieme $S=\{ \underline{v_{1}},\dots \underline{v_{j}} \}$ di vettori di $V\leq\mathbb K^m$ si dice ***Insieme Ortonormale***, se è un **insieme ortogonale** in cui tutti i vettori hanno **norma euclidea** uguale a 1, ossia $\underline{v_{i}}\perp \underline{v_{j}}$ e $\|\underline{v_{i}}\|_{2}=\|\underline{v_{j}}\|_{2}=1\ \forall i\neq j$, $(\underline{v_{i}}|\underline{v_{j}})=0$ e $(\underline{v_{i}}|\underline{v_{i}})=(\underline{v_{j}}|\underline{v_{j}})=1$.
Una ***Base Ortonormale*** di $V$ è una base di $V$ che è anche **insieme ortonormale**, quindi tutti i .

*Osservazione*: Dato un **insieme ortogonale** possiamo ottenere un **insieme ortonormale** rimuovendo eventuali vettori *nulli* di $S$ e normalizzando i *non-nulli*:$$S'=\left\{ \frac{1}{\|\underline{v_{1}}\|_{2}}\cdot \underline{v_{1}},\ \dots \right\}$$
###### Proprietà
Sia $S=\{ \underline{v_{1}},\dots,\underline{v_{t}} \}$ un insieme di vettori di $\mathbb K^m$. Supponiamo che $S$ sia **ortogonale**. Allora:
1. Se $S$ non contiene vettori nulli, allora $S$ è L.I.
2. Se $S$ è *insieme di generatori* di $V\leq\mathbb K^m$, allora togliendo i vettori nulli si ottiene una **base ortogonale** di $V$.

### Complemento Ortogonale
*Def*: Sia $W\leq\mathbb K^m,\ \mathbb K\in \{ \mathbb R,\mathbb C \}$. Il ***complemento ortogonale*** $W^{\perp}$ di $W$ in $\mathbb K^m$ è $$W^\perp=\{ \underline{v}\in\mathbb K^m\ |\ \underline{v}\perp \underline{w}\ \ \forall \underline{w}\in W \}$$
###### Proprietà
Sia $W\leq\mathbb K^m$
1. $W^\perp$ è un sottospazio vettoriale di $\mathbb K^m$
2. $\left(W^\perp\right)^\perp=W$
3. $W\cap W^\perp=\{ \underline{0} \}$
4. $\mathbb K^m=W+W^\perp=^3W\oplus W^\perp$

Per ogni vettore $\underline{v}\in\mathbb K^m$ esistono unici $\underline{w}\in W$ e $\underline{u}\in W^\perp$ tali che $\underline{v}=\underline{w}+\underline{u}$.
$\text{dim }\mathbb K^m=\text{dim }W+\text{dim }W^\perp$ quindi $\text{dim }W^\perp=m-\text{dim }W$.

*Osservazione*: Sia $A\in M_{m,n}(\mathbb C)$. Allora
- $N(A)^\perp=C(A^H)=R(A)$ spazio delle righe di $A$
- $C(A)^\perp=N(A^H)$

### Algoritmo di Gram-Schmidt
*Problema*: Trovare una ***base ortonormale*** di $$W=\ <\underline{v_{1}},\dots,\underline{v_{m}}>\ \leq\mathbb K^n,\ \mathbb K\in \{ \mathbb R,\mathbb C\}$$
1. Porre $S=\{ \underline{v_{1}},\dots,\underline{v_{m}} \}$. $S$ è l'***insieme di generatori*** di $W$.
2. Costruire un **insieme ortogonale di generatori** di $W$$$S'=\{ \underline{w_{1}},\dots,\underline{w_{m}} \}$$a partire da $S$.
3. Togliere eventuali vettori nulli da $S'$ per avere una ***base ortogonale*** $B$ di $W$.
4. Normalizzare i vettori di $B$ per ottenere una ***base ortonormale*** $B^*$ di $W$.

Il punto 2 si può svolgere tramite l'***Algoritmo di Gram-Schmidt***.

###### In  generale
Dato $S=\{ \underline{v_{1}},\dots,\underline{v_{m}} \}$ insieme di generatori di $W\leq\mathbb K^n$.
- Poniamo $\underline{w_{1}}=\underline{v_{1}}$
- $\underline{w_{2}}=\underline{v_{2}}-\alpha_{12}\cdot \underline{w_{1}}$ dove$$\alpha_{12}=\begin{cases}
0\qquad  & \text{se }\underline{w_{1}}=\underline{0} \\
\large \frac{(\underline{w_{1}}|\underline{v_{2}})}{\|\underline{w_{1}}\|_{2}^2} & \text{se }\underline{w_{1}}\neq \underline{0}
\end{cases}$$
- $\underline{w_{3}}=\underline{v_{3}}-\alpha_{13}\underline{w_{1}}-\alpha_{23}\cdot \underline{w_{2}}$<br>
    dove $\quad\alpha_{13}=\begin{cases}0\qquad & \text{se }\underline{w_{1}}=\underline{0} \\ \large \frac{(\underline{w_{1}}|\underline{v_{2}})}{\|\underline{w_{1}}\|_{2}^2} & \text{se }\underline{w_{1}}\neq \underline{0}\end{cases}\qquad$ e $\quad \alpha_{23}=\begin{cases}0\qquad & \text{se }\underline{w_{2}}=\underline{0} \\ \large\frac{(\underline{w_{2}}|\underline{v_{3}})}{\|\underline{w_{2}}\|_{2}^2} & \text{se }\underline{w_{2}}\neq \underline{0}\end{cases}$

In generale:$$\underline{w_{i}}=\underline{v_{i}}-\alpha_{1i}\cdot \underline{w_{1}}-\dots-\alpha_{(i-1)i}\cdot \underline{w_{(i-1)}}$$
con$$\alpha_{ji}=\begin{cases}
0\qquad & \text{se }\underline{w_{j}}=\underline{0} \\
\frac{(\underline{w_{j}}|\underline{v_{i}})}{\|\underline{w_{j}}\|_{2}^2} & \text{se }\underline{w_{j}}\neq \underline{0}
\end{cases}$$
L'insieme $S'=\{ \underline{w_{1}},\dots,\underline{w_{m}} \}$ è **insieme ortogonale di generatori** di $W$.