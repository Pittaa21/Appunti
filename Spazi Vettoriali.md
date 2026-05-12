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
1. **Vettori colonna**<br>$V=\mathbb R^n\{\underline{u}=\}$
2. **Spazio Vettoriale** dei **Vettori Riga**<br>$V=\mathbb R_{n}$ o $\mathbb C_{n}$<br>In questi casi<br>$\underline{0}=\begin{pmatrix}0 & \dots & 0\end{pmatrix}$<br>se $\underline{u}=\begin{pmatrix}u_{1} & \dots & u_{n}\end{pmatrix},\ -\underline{u}=\begin{pmatrix}-u_{1} & \dots & -u_{n}\end{pmatrix}$
3. **Spazio vettoriale** delle **Matrici**<br>$V=$
4. **Spazio Vettoriale** dei **Polinomi** a coefficiente in $\mathbb R$ o $\mathbb C$<br>$V=\mathbb R[x]$ o $\mathbb C[x]$<br>$=\{f(x)=a_{0}+a_{1}x+a_{2}x^2+\dots+a_{n}x^n|ai\in \mathbb K\}$<br>In questi casi<br>$\underline{0}$ è il polinomio nullo $f(x)=0$<br>se $f(x)=a_{0}+a_{1}x+\dots+a_{n}x^n,\ -f(x)=-a_{0}-a_{1}x\dots-a_{n}x^n$
5. **Spazio Vett** dei **Polinomi di Grado** al più $n$<br>$V=\mathbb R_{n}[x]=\{f(x)\in\mathbb[x]\ |\ deg(f(x))\le n\}$<br>$V=\mathbb C_{n}[x]$

Osserviamo che le operazioni *somma* e *per* sono ben definite su $V$:
se $f(x),g(x)\in\mathbb K_{n}[x]$ allora
- $deg\left(f(x)+g(x)\right)\le \text{max}\{deg(f(x)),deg(g(x))\}\le n$
- $\forall \alpha\ne 0,\alpha\in\mathbb K,deg(\alpha \cdot f(x))=deg(f(x))\le n$
- $deg(0\cdot f(x))=deg(\underline{0})=-\infty\le n$

*Nota*: $deg(f(x))$ vuol dire il grado di $f(x)$ se $f(x)=x^2,deg(f(x))=2$

#### Sottospazi Vettoriali
*Definizione*: Sia $V$ uno spazio vettoriale su $\mathbb K$. Un **sottospazio vettoriale** di $V$ è un sottoinsieme $U$ di $V$ tale che:
1. $\underline{0}\in U$
2. $\underline{u_{1}}+\underline{u_{2}}\in U\ \forall \underline{u_{1}},\underline{u_{2}}\in U$ ($U$ è chiuso per la somma)
3. $\alpha \cdot \underline{u}\in U\ \forall \underline{u}\in U,\ \forall \alpha\in\mathbb K$ ($U$ è chiuso per prodotto per scalare)<br>Scriviamo $U\le V$ 

IMG

*Nota*: 
- $U\subseteq V$, $U$ è sottoinsieme di $V$<br>$U\le V$, $U$ è sottospazio di $V$
- se $U\le V$ allora $U$ è spazio vettoriale su $\mathbb K$ con le operazioni che si ottengono restringendo ad $U$ quelle di $V$.