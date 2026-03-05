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


### Inverso
Sia *z* $\in\mathbb C$,  *z* $\ne$ 0.
L'inverso di *z* è il numero complesso $\large\frac 1{\text z}$
Per trovare la forma algebrica di bisogna moltiplicare e dividere $\large\frac 1{\text z}$ per $\bar{\text z}$:
$$
\large \frac1{\text z} = \frac1{\text z}\cdot \bar{\text z} \cdot \frac1{\bar{\text z}} = \frac{\bar{\text z}}{\text z\cdot \bar{\text z}} = \frac{\bar{\text z}}{|\text z|^2}
$$

## Divisione in $\mathbb N$ e $\mathbb Z$ 
---
In $\mathbb N$ 
Siano *a*,*b* $\in\mathbb N$  con *b* $\ne$ 0.  Allora **esistono** e sono **unici** due numeri *q* (*quoziente*) e *r* (*resto*)
tali che:
$$
\large \text a = \text q \cdot \text b + \text r\qquad 0\le\text r<\text b
$$
---
In $\mathbb Z$
Siano *a*,*b* $\in\mathbb Z$  con *b* $\ne$ 0.  Allora **esistono** e sono **unici** due numeri *q* (*quoziente*) e *r* (*resto*)
tali che:
$$
\large \text a = \text q \cdot \text b + \text r\qquad 0\le\text r<\text |b|
$$
*Nota*: il resto è sempre positivo o zero.

---

## MCD (in $\mathbb N$ e $\mathbb Z$)
Siano *a*,*b* $\in\mathbb{Z}$  con *b* $\ne$ 0.
Si dice che **b divide a**, e si scrive *b* | *a*   se *a* = q $\cdot$ *b*  per un opportuno *q* intero (il resto è zero).

#### Proprietà
---
In $\mathbb Z$
Siano *a*,*b*,*c* $\in\mathbb{Z}$  con *a* $\ne$ 0, *b* $\ne$ 0.
1. Se *a* | *b* e *b* | *a* allora *a* = $\pm$ *b* 
2. Se *a* | *b* e *a* | *c* allora *a* | (*b* + *c*)
3. Se *a* | *b* e *b* | *c* allora *a* | *c*
---
In $\mathbb N$
Siano *a*,*b* $\in\mathbb{N}$  non entrambi nulli.
Si dice che *d* $\in\mathbb N$ è un **massimo comun divisore** di *a* e *b* se valgono:
1. *d* | *a* e *d* | *b*  (*d* è un divisore comune di *a* e *b*)
2. se *z* $\in\mathbb N$ è tale che *z* | *a* e *z* | *b*  allora  *z* | *d*   (*d* è multiplo di tutti i divisori di *a* e *b*)
---
**Osservazione**: se *a*,*b* $\in\mathbb{N}$  non entrambi nulli, allora esiste un *unico* **Massimo Comun Divisore** che si indica con *MCD (a,b)* 

In $\mathbb Z$
Abbiamo definizione simile di massimo comun divisore, ma *non* vale più l'*unicità*.  Infatti se *d* è mcd (*a*,*b*) anche *-d* lo è.

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