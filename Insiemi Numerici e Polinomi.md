## Numeri Complessi

$i$  = unità immaginaria tale che $i^2$ = -1

un **numero complesso** è un numero della forma algebrica:

---

$$
Z=a+i\cdot b\qquad \text{con }a,b\in\mathbb{R} 
$$

---

L'**Insieme dei numeri complessi** è 
$$
\mathbb{C}=\{a+i\cdot b\ |\ a,b\in\mathbb{R}\}
$$


## MCD
###### Calcolo dei Massimi Comun Divisori in $\mathbb{Z}$
Siano $a,b\in\mathbb{Z}$ non entrambi nulli.

1° Metodo:      
			   |$a$|$,$|$b$|$\in\mathbb{N}$ e MCD(|$a$|,|$b$|) 

2° Metodo:      
			   Eseguiamo le divisioni successive dell'algoritmo di *Euclide* in $\mathbb{Z}$
			   **N.B.** tutti i resti devono essere numeri naturali. I massimi comun divisori sono dati dall'ultimo resto *non nullo* $d$ e da $-d$. 

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
