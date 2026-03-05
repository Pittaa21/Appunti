## Numeri Complessi

*i*  = unità immaginaria tale che *i*$^2$ = -1

un **numero complesso** è un numero della forma algebrica:

---

$$
\large Z=a+i\cdot b\qquad \text{con }a,b\in\mathbb{R} 
$$

---


L'**Insieme dei numeri complessi** è 
$$
\large\mathbb{C}=\{a+i\cdot b\ |\ a,b\in\mathbb{R}\}
$$
I **numeri complessi** si possono rappresentare con il piano cartesiano, dove *z* viene rappresentato dalle coordinate (*a*,*b*)

![[complex.svg|center]]

---

#### Osservazioni
1. *Tutti* i numeri reali sono numeri complessi
$$
\large\mathbb{N}\subseteq\mathbb{Z}\subseteq\mathbb{Q}\subseteq\mathbb{R}\subseteq\mathbb{C}
$$
2. I numeri con a = 0, sono detti ***Immaginari Puri***

### Somma e Prodotto di Numeri Complessi
Siano *z* = a + *i* $\cdot$ b  e  *w* = c + *i* $\cdot$ d  due numeri complessi.

- *z* + *w* = (a + *i*b) + (c + *i*d) = (a + c) + *i* $\cdot$ (b + d)

![[complexsum.svg|center]]

- *z* $\cdot$ *w* = (a + *i*b) $\cdot$ (c + *i*d) = (a$\cdot$c - b$\cdot$d) + *i* $\cdot$ (b$\cdot$c + a$\cdot$d)

### Coniugato
Definizione:  	Sia *z* = a + *i*b un numero complesso. Il **Coniugato di** *z* è il numero complesso

---
$$
\large\bar{z} = a-i\cdot b
$$
---
*Es*:      z = 2 + 3*i*        $\bar{\text{z}}$ = 2 - 3*i*
Nel piano cartesiano $\bar{\text{z}}$ è il punto simmetrico a $\text{z}$ rispetto alle ascisse.

##### Proprietà Coniugato
Siano *z*,*w* $\in\mathbb{C}$.
1. $\overline{\text{z}+\text{w}}$  = $\bar{\text{z}}$ + $\bar{\text{w}}$
2. $\overline{\text{z}\cdot\text{w}}$  = $\bar{\text{z}}$ $\cdot$ $\bar{\text{w}}$
3. $\overline{\bar{\text z}}$ =  $\text z$
4. $\text z$ =  $\bar{\text z}\qquad \Leftrightarrow\qquad\text z \in \mathbb R$

### Modulo
Sia *z* = a + *i*b un numero complesso. Il **Modulo** di *z* è il numero.

---
$$
\large\left|\text z\right| = \sqrt{a^2+b^2}
$$
---



#### Proprietà Modulo
1. $|\text z|^2$ = $\text z \cdot \bar{\text z}\qquad \forall\text z\in\mathbb C$
2. $|\text z \cdot\text w|$ = $|\text z|\cdot|\text w|\qquad\forall\text z,\text w\in\mathbb C$
3. $|\text z +\text w|\ \le\ |\text z| +|\text w|\qquad\forall\text z,\text w\in\mathbb C$            (*Disuguaglianza Triangolare*)

### MCD
###### Calcolo dei Massimi Comun Divisori in $\mathbb{Z}$
Siano *a*,*b* $\in\mathbb{Z}$ non entrambi nulli.

1° Metodo:      
			   |$a$|$,$|$b$|$\in\mathbb{N}$ e MCD(|$a$|,|$b$|) 

2° Metodo:      
			   Eseguiamo le divisioni successive dell'algoritmo di *Euclide* in $\mathbb{Z}$
			   **N.B.** tutti i resti devono essere numeri naturali. I massimi comun divisori sono dati dall'ultimo resto *non nullo* $d$ e da $-d$. 
vault
Esempio: MCD(-274, 110)
		1° Metodo
					 274 = 2 $\cdot$ 110 + *54*
					110 = 2 $\cdot$ 54 + ***2***
					54 = 27 $\cdot$ 2 + *0*
		MCD(274,110) = 2
		2° Metodo
					-274 = (-3) $\cdot$ 110 + *56*
					110 = 1 $\cdot$ 56 + *54*
					56 = 1 $\cdot$ 54 + ***2***
					54 = 27 $\cdot$ 2 + *0*
		MCD(274,110) = 2

### TEOREMA (IDENTITÀ DI BEZOUT)
Dati $a,b\in\mathbb{Z}$ non entrambi nulli *esistono* due numeri interi $m,n\in\mathbb{Z}$ tali che se $d$ è un massimo comun divisore di $a$ e $b$ allora:

---
$$
\large d=m\cdot a + n\cdot b
$$
---

Esempio:
			a = 10,  b = 4,  d = 2
			2 = 1 $\cdot$ 10 + (-2) $\cdot$ 4
			2 = (-1) $\cdot$ 10 + 3


#### Zeri di Polinomi
Sia *S* uno tra $\mathbb Z,\mathbb Q,\mathbb R,\mathbb C$.
Un numero $\text z \in\mathbb C$ si dice **zero** (o radice) del polinomio f(x) $\in$ S[x] se
$$
\large F(\text z) = 0
$$
Se *z* $\in\mathbb R$, si dice che *z* è **Zero Reale**.

*z* è soluzione dell'equazione
$$
\large a_0 + a_1x+ ... + a_nx^n = 0
$$

**Teorema di Ruffini**: Siano f(x) $\in$ S[x] e *z* $\in\mathbb C$.     *z* è zero di f(x) $\Leftrightarrow$ (x - *z*) divide f(x) in $\mathbb C$.    Quindi esiste q(x) $\in\mathbb C$[x] tale che:   f(x) = q(x) $\cdot$ (x - *z*)

Esempio:     f(x) = $x^2 + x -2\qquad\Rightarrow\qquad (x-1)\cdot(x-2)$ 
			prendo *1* come zero se (x - *1*) divide $(x-1)\cdot(x-2)$  allora *1* è uno zero di f(x), che in questo caso è vero $\checkmark$

**Proprietà**: Sia f(x) $\in\mathbb R$[x].   Se *z* $\in\mathbb C$ è uno zero di *f*, allora ache $\bar{\text z}$ è zero di *f*.

Nei polinomi a coefficienti reali gli zeri *non-reali* si trovano sempre in coppie. Se un polinomia a


#### Teorema Fondamentale dell'Algebra
Ogni polinomio di grado *n* > 0   allora  ha esattamente **n zeri complessi** (contati con le loro molteplicità quindi anche con *n* uguali) e quindi ha **n soluzioni complesse** (contando le molteplicità).  

Di conseguenza ogni polinomio di grado *n* > 0 è il prodotto di *n* polinomi di grado 1 a coeff. complessi
$$
\large f(x) a_n\cdot (x)
$$

Esempio:
						Polinomi reali di 1° grado
$$
\large F(x) = bx+c\qquad b,c\in\mathbb R
$$
Il teorema dice che $F$ ha un unico zero *z* con  *z* = -$\large\frac cb$ 
						Polinomi reai di 2° grado
$$
f(x) = ax^2 + bx +c\qquad a,b,c\in\mathbb R
$$
Il teorema dice che ci sono sempre 2 zeri complessi *z*$_1$ e *z*$_2$
$\Delta = b^2-4ac$   *discriminante* 

Se $\Delta < 0$ allora non ci sono soluzioni nei reali, ma *z*$_1$,*z*$_2\in\mathbb C \setminus \mathbb R$  