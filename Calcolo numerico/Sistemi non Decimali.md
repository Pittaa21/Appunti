# Conversione da base $N$ a base $M$

> [!info] Obiettivo
> Dato $x > 0$ (per semplicità) e nota la rappresentazione $(x)_N$, vogliamo trovare $(x)_M$.

Vogliamo che:
$$
\begin{align*}
x &= x_n N^n + x_{n-1} N^{n-1} + \cdots + x_0 + x_{-1} N^{-1} + \cdots + x_{-r} N^{-r} \\
&= y_m M^m + y_{m-1} M^{m-1} + \cdots + y_0 + y_{-1} M^{-1} + \cdots + y_{-q} M^{-q}
\end{align*}
$$

Si procede separatamente per parte *intera* e *frazionaria*.

## Conversione della parte intera

Iteriamo lo schema con divisione intera per $M$:
$$
\begin{align}
y_0 &:= x \bmod M, \quad x = q_0 M + y_0 \\
y_1 &:= q_0 \bmod M, \quad q_0 = q_1 M + y_1 \\
&\vdots \\
y_m &:= q_m \bmod M, \quad q_m = y_m < M
\end{align}
$$

**NB**: $x \bmod M$ è il ***resto*** *della divisione intera*.

Allora:
$$
(x_{\text{int}})_M = y_m y_{m-1} \dots y_0
$$

## Conversione della parte frazionaria

Si procede moltiplicando per $M$:
- calcolo $M \cdot x_{\text{fraz}}$;
- sottraggo (e annoto) la parte intera del numero ottenuto;
- se ottengo $0$ ho finito.

## Esempi

> [!example] Convertire $(10011010010)_2$ in base $10$
> $$
> 2^{10} + 2^7 + 2^6 + 2^4 + 2^2 = 1024 + 128 + 64 + 16 + 2 = (1234)_{10}
> $$

> [!example] Convertire $(1234)_{10}$ in binario
> $$
> 1234:2=617 \quad 617:2=308 \quad 308:2=154 \quad 154:2=77 \quad \dots
> $$
> Risultato: $(1234)_{10} = (10011010010)_2$.

> [!example] Convertire $(0.0625)_{10}$ in binario
> $$
> \begin{aligned}
> 0.0625 \times 2 &= 0.125 \quad \to 0 \\
> 0.1250 \times 2 &= 0.250 \quad \to 0 \\
> 0.2500 \times 2 &= 0.5 \quad \to 0 \\
> 0.5000 \times 2 &= 1.0 \quad \to 1 \\
> 0.0000 \times 2 &= 0
> \end{aligned}
> $$
> Quindi $(0.0625)_{10} = (0.0001)_2$.

> [!warning] $0.1$ è *periodico* in base 2
> $$
> (0.1)_{10} = (0.0001100110011\ldots)_2
> $$
> Ha un numero illimitato di cifre e **non può** essere rappresentato *esattamente* in un calcolatore binario.

---

# Numeri macchina

## Interi macchina (IEEE 754)

Tipici: *int32* (32 bit) o *int64* (64 bit). Il primo bit a sinistra è riservato al segno: $0 \to +$, $1 \to -$.

Il **massimo** intero rappresentabile con $n$ bit:
$$
I_{\max,n} = (111\dots1)_2 = \sum_{i=0}^{n-1} 2^i = 2^n - 1.
$$

> [!warning] **Overflow**
> Avviene quando il risultato non è rappresentabile e il *riporto* va a scriversi sul **bit di segno**.

> [!example] $7+2$ calcolato da una lavatrice
> Usando interi macchina a 4 bit ($n=3$):
> $$
> \begin{array}{c}
> 0111 \\
> 0010 \\
> \hline
> 1001
> \end{array} = -1
> $$
> Quindi $7+2 = -1$! Questo problema si chiama **overflow**.

## Floating point (IEEE 754)

Usando la notazione binaria, un numero $x \neq 0$ può essere scritto come:
$$
(x)_2 = (-1)^s \times 2^{e-b} \times 1.f
$$
dove:
- $s$ è il *segno*
- $e-b$ è l'*esponente* con deviazione (**bias**) $b$, che serve ad avere $e \ge 0$ così non serve memorizzare il segno di $e$
- $1.f$ è la *mantissa*
- se $x \neq 0$ non ha senso memorizzare l'$1$ (**hidden bit**), quindi $0$ ha bisogno di una convenzione particolare

### Tabella riassuntiva IEEE 754

|                     | 32 bit                             | 64 bit                             |
| ------------------- | ---------------------------------- | ---------------------------------- |
| Bit totali          | 32                                 | 64                                 |
| Bit segno           | 1                                  | 1                                  |
| Bit esponente       | 8                                  | 11                                 |
| Bit mantissa        | 23                                 | 52                                 |
| Bias $b$            | 127                                | 1023                               |
| Intervallo $e$      | $0 < e < 255$                      | $0 < e < 2047$                     |
| $e=0, f=0$          | $\pm 0$                            | $\pm 0$                            |
| $e=0, f>0$          | denormalizzato                     | denormalizzato                     |
| $e=255, f=0$        | $\pm \infty$                       | $\pm \infty$                       |
| $e=255, f>0$        | NaN (Not-a-Number)                 | NaN                                |

### Arrotondamento e troncamento

Cosa facciamo con le cifre in più?

- **Troncamento**: le cifre oltre a quelle memorizzabili non vengono considerate
- **Arrotondamento**: l'ultima cifra decimale è memorizzata
  - *aumentata* se la cifra successiva è $1$
  - *non aumentata* se la cifra successiva è $0$

## Errore e norme

### Errore assoluto e relativo

Vogliamo rappresentare o calcolare $x \in \mathbb{R}$ o $x \in \mathbb{R}^m$, non invece calcolare o rappresentare $\tilde{x} \approx x$.

- Errore **assoluto**: $|\tilde{x} - x|$ se $x \in \mathbb{R}$.
- Se $x \in \mathbb{R}^n$ useremo $||\tilde{x} - x||$, con $||\cdot||$ che è una **norma** su $\mathbb{R}^n$.

> [!info] ==Definizione== di norma
> Sia $V$ uno spazio vettoriale e $||\cdot||: V \to \mathbb{R}_{\ge 0}$. Allora $||\cdot||$ è una norma se:
> 1. $||\lambda v|| = |\lambda| \, ||v|| \quad \forall \lambda \in \mathbb{R}, v \in V$
> 2. $||v|| = 0 \Rightarrow v = 0_V$
> 3. $||u+v|| \le ||u|| + ||v||$ (***disuguaglianza triangolare***)

È una generalizzazione della *norma euclidea*. Per $v \in \mathbb{R}^n$, $v = (v_1, \dots, v_n)^T$:
$$
||v|| = \sqrt{v_1^2 + v_2^2 + \dots + v_n^2} = \left( \sum_{d=1}^n v_d^2 \right)^{1/2}
$$

Norma $p$:
$$
||v||_p = \left( \sum_{d=1}^n |v_d|^p \right)^{1/p} \quad p \ge 1
$$

Norma *infinito*:
$$
||v||_\infty := \max_i |v_i|
$$

> [!note] **Equivalenza delle norme**
> Sia $\{v_k\}$ una successione in $\mathbb{R}^n$, e siano $||\cdot||_a$, $||\cdot||_b$ due norme. Allora:
> $$
> v_k \to v \text{ rispetto a } ||\cdot||_a \iff v_k \to v \text{ rispetto a } ||\cdot||_b.
> $$

Errore *relativo* per vettori:
$$
\text{Err}(\tilde{v}, ||\cdot||) := \frac{||\tilde{v} - v||}{||v||}
$$

### Floating point: successivo e precedente

Poiché $\mathbb{F}_{32}$ e $\mathbb{F}_{64}$ sono insiemi finiti e ordinati, posso definire *successivo* e *precedente*:
$$
\text{succ}(x) = \min \{ y \in \mathbb{F} : y > x \} \quad \forall x \in \mathbb{F}
$$
$$
\text{prec}(x) = \max \{ y \in \mathbb{F} : y < x \} \quad \forall x \in \mathbb{F}
$$

Quanto vale $\text{succ}(x) - x$?

Se $x = (-1)^s \cdot 2^{e-b} \cdot 1.f$, allora:
$$
\text{succ}(x) - x = 2^{e-b-n}
$$

### Errore di rappresentazione

Con **troncamento**:
$$
|x - \text{fl}^T(x)| \le |\text{succ}(\tilde{x}) - \tilde{x}| = 2^{e-b-n}
$$

Errore *relativo* di **troncamento**:
$$
\left| \frac{x - \text{fl}^T(x)}{x} \right| \le 2^{-n}
$$

Con **arrotondamento**:
$$
|x - \text{fl}^A(x)| \le \frac{1}{2} |\text{succ}(\tilde{x}) - \tilde{x}| = 2^{e-b-n-1}
$$

Errore *relativo* di **arrotondamento**:
$$
\left| \frac{x - \text{fl}^A(x)}{x} \right| \le 2^{-n-1}
$$

> [!info] Precisione di macchina
> $$
> \epsilon_{\text{mach}} := \{ \epsilon > 0 : \text{fl}(1+\epsilon) > 1 \}
> $$

### Operazioni macchina

==Definizione==:
$$
\Delta: \mathbb{R} \times \mathbb{R} \to \mathbb{R} \quad (+,\cdot)
$$
$$
\mathbb{R} \times \mathbb{R}\setminus\{0\} \to \mathbb{R} \quad (:)
$$

Operazione macchina *associata*:
$$
\Delta: \mathbb{R} \times \mathbb{R} \to \mathbb{F}, \quad (x,y) \mapsto \Delta(x,y)
$$

#### Errore relativo di moltiplicazione

$$
\text{Err}_{\text{rel}}(x \odot y) = \frac{|x \odot y - x \cdot y|}{|x \cdot y|} = \frac{|\text{fl}(\text{fl}(x) \cdot \text{fl}(y)) - x \cdot y|}{|x \cdot y|}
$$

Comportamento al primo ordine non dipende da $x, y$. La moltiplicazione è **stabile**.

#### Errore relativo di somma

$$
\text{Err}_{\text{rel}}(x \oplus y) = \frac{|\text{fl}(\text{fl}(x) + \text{fl}(y)) - (x+y)|}{|x+y|}
$$
(Il comportamento è analogo ma con cancellazione numerica.)