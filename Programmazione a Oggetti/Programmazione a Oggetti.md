# Caratteristiche del linguaggio C++

> [!info] Caratteristiche principali
> - Compilato
> - Tipizzazione forte statica (*strongly typed*)
> - No garbage collector
> - Standardizzato (C++17, C++20 in progress)
> - General-purpose e molto diffuso (Adobe, Mozilla, MySQL, Microsoft, Chromium, giochi…)
> - Efficienza
> - Supporto all’overloading degli operatori
> - Ampia libreria standard

## Classi e Oggetti

- Il concetto OO di **classe** implementa gli **ADT** (Abstract Data Type).
- Una classe contiene:
  1. **Campi dati** (stato)
  2. **Metodi** (operazioni)
- Le variabili di tipo classe vengono dette **oggetti**.
- Ogni oggetto memorizza i propri valori dei campi dati.
- I metodi sono un’unica copia in memoria, condivisa da tutti gli oggetti.

### Definizione di una classe

![[carbon(6) 1.svg]]

- `private`: accessibile solo dai metodi della classe (default).
- `public`: interfaccia pubblica, accessibile dall’esterno.

### Implementazione dei metodi

![[carbon.svg]]

### Metodi inline

Se definiti direttamente dentro la classe, i metodi sono **inline**:

![[carbon(7).svg]]

> [!note]
> Un metodo inline evita l’overhead di chiamata: il compilatore inserisce il codice della funzione nel punto di chiamata.

### Accesso ai membri

![[carbon(8).svg]]

### Il puntatore `this`

- È un parametro implicito di tipo `Classe*` che punta all’oggetto di invocazione.
- `this->sec` equivale a `(*this).sec`.
- A volte è necessario esplicitarlo, ad esempio per restituire l’oggetto stesso:

```cpp
A A::f() { a = 5; return *this; }
```

---

## Information Hiding

> [!info] Definizione
> Principio di segregazione delle decisioni progettuali che hanno maggiori probabilità di cambiare, proteggendo il resto del programma da modifiche estese.

- Si realizza fornendo un’**interfaccia stabile** che nasconde l’implementazione.
- Impedisce l’accesso a certi aspetti di una classe tramite `private` o policy di esportazione.
- Parte **pubblica** = interfaccia (documentazione).
- Parte **privata** = implementazione nascosta.
- Dall’esterno si accede solo alla parte pubblica.
- I metodi della classe possono accedere alla parte privata di *qualsiasi* oggetto della classe (non solo di quello di invocazione).

## ADT – Abstract Data Type

> [!info] Definizione
> Tipo di dato le cui istanze possono essere manipulate esclusivamente tramite la semantica del dato, non dalla sua implementazione.

- Distinzione netta tra:
  - **Interfaccia**: operazioni fornite (metodi pubblici)
  - **Implementazione interna**: modo in cui lo stato è conservato e le operazioni manipolano i dati
- L’inaccessibilità dell’implementazione è detta **incapsulamento** o **information hiding**.
- ADT = **Valori + operazioni**.
- Esempio di ADT primitivo: `int`.
- `struct` del C/C++ non rispetta il concetto di ADT (membri pubblici di default).

---

## Namespace

> [!info] Definizione
> Meccanismo che permette di incapsulare nomi che altrimenti inquinerebbero il namespace globale. Non è disponibile in C.

### Dichiarazione e uso

```cpp
namespace SPAZIO_UNO {
    struct Complex { /* ... */ };
    void f(Complex c) { /* ... */ }
}
```

Accesso con operatore di scoping `::`:

```cpp
SPAZIO_UNO::Complex var1;
SPAZIO_UNO::f(var1);
```

### Direttiva `using namespace`

```cpp
using namespace SPAZIO_UNO;
Complex var1; // equivale a SPAZIO_UNO::Complex
f(var1);
```

> [!warning]
> Generalmente sconsigliata perché rende visibili tutti i nomi e può creare ambiguità.

### Namespace `std`

- Tutte le componenti della libreria standard C++ sono nel namespace `std`.
- Preferibile usare lo scoping esplicito:

```cpp
#include <iostream>
int main() {
    std::cout << "Hello World" << std::endl;
}
```

- `using namespace std;` è considerata una scelta discutibile.

---

### Stringhe in STL

- `string` è una classe della libreria standard STL.
- È un’istanza di un template: `typedef basic_string<char> string`.
- Esempio d’uso:

```cpp
string st1;        // costruttore: stringa vuota
string st2(st);    // costruttore di copia
cout << st.size(); // metodo size()
```

#### Esempio di ADT: Numeri Complessi

- **Rappresentazione cartesiana:** `struct comp { double re, im; };`
- Operazioni tipiche: `inizializzaComp`, `reale`, `immag`, `somma`.
- **Rappresentazione polare:** modulo `mod` e argomento `arg`.
  - `mod = sqrt(r*r + i*i)`
  - `arg = atan(i/r)`
  - `reale() { return mod*cos(arg); }`
  - `immag() { return mod*sin(arg); }`
- La classe nasconde la rappresentazione interna e fornisce un’interfaccia pubblica.

---

### Compilatore

`g++` è l’alias per `gcc -xc++`.

---

### Reference
> [!info] **Definizione**: una *reference* è un alias, ossia un altro nome di una variabile già esistente. Quando una *reference* è inizializzata con una variabile, sia la variabile sia la *reference* possono essere usate per riferirsi alla variabile.

```c++
int x=2;
int& a = x; // ALIAS
```

#### Differenze coi puntatori
- Non si possono avere *reference* `NULL`. Le *reference* devono essere sempre connesse ad una cella di memoria
- Quando una *reference* è inizializzata ad un *oggetto* non può cambiare riferimento. I puntatori li puoi invece spostare tra oggetti.
- Una *reference* deve essere inizializzata quando viene creata, i puntatori quando si vuole invece.

```c++
int i;
int& r=i;
i=5;
cout<<"I: "<<i<<" R: "<<r<<endl; // 5 5

void swap(int& x, int& y){
    int tmp = x;
    x = y;
    y = tmp;
}

int a = 1, b = 2;
cout<<a<<" "<<b<<endl; // 1 2
swap(a,b);
cout<<a<<" "<<b<<endl; // 2 1
```


> Una funzione può anche ritornare *reference* in modo simile ai puntatori.
> Quando una funzione ritorna una *reference*, ritorna un puntatore implicito al suo valore di ritorno

```c++
int v[] = {2, 4, 3, 5}
int& setValue(int i){
    return v[i] // ritorna una reference al i-esimo elemento
}

setValue(1) = 9;
```

> [!warning] Non è legale ritornare una *reference* ad una variabile locale:

```c++
int& f(int& a){
    int q;
    // return q;   errore di compilazione
    return a;  // sicuro
}
```

```c++
int x=2
int& a=x;
int& b=2; // non si può fare
a=5;
int y=3;
a=y;   // al valore di x ci assegno il valore di y

int* p = &x;
*p=5;
int y=3;
p=&y;

int * const c = &x;
*c=5; // si
int y=3;
c=&y; // no

int & const d = x; // tipo illegale
```

```c++
int x=2;
const int& r=x; //riferimento a tipo costante
r=5;  //illegale
int y=3;
r=y;  // illegale

const int& r1 = 4; // si
r = 5; //no
int y=3;
r=y; //no
```

#### Parametro per valore - per riferimento costante
```c++
class C{
    int a[1000];
}

bool perValore(C x){return true;}
bool perRiferimentoCostante(const C& x){return true;}

int main(){
    C obj;
    for(int i=0; i<1000000; i++) perValore(obj); //3 sec
    for(int i=0; i<1000000; i++) perRiferimentoCostante(obj); //0.03 sec
}
```

---
### Campi Statici
L'inizializzazione dei campi statici si fa fuori dalla classe ed è sempre richiesta
```c++
class orario{
    public:
    static int secOra;
}

int orario::secOra = 3600;
```

### Operator Overloading
```c++
class orario{
    public:
    orario operator+(orario) const;
}

orario orario::operator+(orario o) const{
    orario aux;
    aux.sec = (sec + o.sec) % 86400;
    return aux;
}

int main{
    orario ora(22,45);
    orario DUE_E_QUARTO(2,15);
    ora = ora + DUE_E_QUARTO;
}
```

==Regole Overloading==
1. Non si può cambiare
    - posizione
    - numero operandi
    - precedenza e associatività
2. Tra gli argomenti deve esserci almeno un tipo definito dall'utente
3. `=`, `[]` e `->` si possono sovraccaricare solo come metodi *interni*
4. Non si può sovrascrivere: `.`, `::`, `sizeof`, `typeid`, i cast e l'*operatore condizionale ternario* `? :`
5. `=`, `&` e `,` hanno una versione standard

***Operatore Condizionale Ternario***
`boolExpr ? expr1 : expr2;`

```c++
orario ora = (day == SUNDAY) ? 15 : 9;

int max(int x, int y){
    return x>y ? x : y;
}
```

Il costruttore di copia `C(const C&)` viene invocato automaticamente quando:
1.  Un oggetto viene dichiarato ed inizializzato da un altro oggetto della stessa classe:
   ```c++
   orario adesso(14,30);
       orario copia = adesso; 
   ```
   2. Un oggetto viene passato per valore come parametro di una funzione:
```c++
       ora = ora.Somma(DUE_QUARTO);
       
       orario orario::Somma(orario o) const {
           orario aux;
           aux.sec = (sec+ o.sec) % 86400;
           return aux;
       }
```
3. Una funzione ritorna per valore tramite l'istruzione `return` un oggetto

Esiste un'ottimizzazione di default per `g++` che quando si crea un oggetto temporaneo *inutile* usato per indirizzare un nuovo oggetto dello stesso tipo (*costruzione di copia*), il temporaneo non viene creato.

==Osservazione==: L'operatore di default per la classe X assegna membro per membro ai suoi soggetti. Se il soggetto è un array, **ogni elemento** è assegnato in modo appropriato al tipo dell'elemento.
```c++
class V{
    public:
        int vett[10];
}

int main(){
    V x,y;
    x.vett[2]=1;
    y=x; // si può fare
    int a[10], b[10];
    a[1]=0;
    b=a; // errore compilazione
}
```

##### Operatore Output `<<`

Con **overloading** *interno*:
```c++
std::ostream& orario::operator<<(std::ostream& os) const{
    return os<<Ore()<<':'<<Minuti()<<':'<<Secondi();
}
```

```c++
orario tre(15,0), quattro(16,0);
quattro<<((tre<<cout)<<" sono prima delle ");
```

Con **overloading** *esterno* alla classe:
```c++
ostream& operator<<(ostream& os, const orario& o){
    return os<<o.Ore()<<':'<<o.Minuti()<<':'<<o.Secondi();
}
```

```c++
orario tre(15,0), dodici(12,0);
cout << "Ora sono le "<<tre<<endl; // Ora sono le 15:0:0
cout << "fra dodici ore sono le "<<tre+dodici<<endl; // fra dodici ore sono le 3:0:0
```

### Macro
Il processore di *c* e *cpp* da la possibilità di includere **file di header** (`#include`), espansioni **macro** (`#define`), **compilazione condizionale** e linee di controllo.



##### Problema di inclusione multipla di file header
```c++
// file C.h
class C{
    public:
        int x;
};

// file D.h
#include <iostream>
#include "C.h"
class D{
    public:
        int x;
        void print(const C& c) const{std::cout<<x+c.x;};
};

//file main.cpp
#include "C.h"
#include "D.h"

int main(){
    C c; D d;
    d.print(c);
}
```

Tramite `ifdef` e `ifndef` che corrispondono a `if defined` e `if !defined`, permettono di verificare se un *identificatore* è stato definito o no.
> [!example] Esempio
 ```c++
 #ifndef ORARIO_H
 #define ORARIO_H
 class orario{
 }
 #endif
 ```

#### Make
Il **make** è un tool che automatizza la creazione di file che dipendono da altri file, risolvendo le *dipendenze* e invocando programmi esterni.

---

### Modularizzazione
Per quanto riguarda la programmazione a oggetti, significa un oggetto ha all'interno di un altro oggetto (**has-a**).

> [!example] Esempio

```c++
  #define TELEFONATA_H
  #include <iostream>
  #include "orario.h"
  
  class telefonata{
      private:
          orario inizio, fine; // has-a
          int numero;
      public:
          telefonata(orario, orario, int);
          telefonata();
  };

```

Invocazione **esplicita** del costruttore di copia
```c++
telefonata::telefonata() : numero(0) {}
```

L'ordine con cui si inizializzano i campi di una classe, solitamente viene usato anche per il costruttore di default.

### Container
È una classe che è una *collezione di oggetti*. Sono usati per contenere oggetti e sono organizzati secondo delle **regole di accesso** specifiche. La dimensione del *container* dipende dal numero di oggetti che contiene.
I *container* richiedono:
- Un **costruttore**, per creare un container vuoto
- metodi per inserire oggetti al suo interno
- metodi per eliminare oggetti dal container
- **clear**, per rimuovere tutti gli oggetti dentro il container
- metodi per accedere ai suoi oggetti
- **count** per accedere al numero di oggetti in esso
I container sono solitamente implementati con gli *iteratori*.
Per esempio delle classi contenitori della libreria standard sono: `string`, `list`, `vector`, `map` e `set`.

#### Linked List
I nodi si definiscono come tipo di dato (*classe*) non più *struct*:
```c++
// bolletta.h
class bolletta{
public:
    bolletta();
    bool Vuota() const;
    void Aggiungi_Tel(const telefonata&);
    void Togli_Tel(const telefonata&);
    telefonata get_Una();
private:
    class nodo{
        public:  // pubblico solo all'interno della classe bolletta
            nodo();
            nodo(const telefonata&, nodo*);
            telefonato info;
            nodo* next;
    }
    nodo* first; // field della classe bolletta
}
```

```c++
// bolletta.cpp
#include "bolletta.h";

bolletta::nodo::nodo() : next(nullptr) {}; // costruttore di default per il nodo
bolletta::nodo::nodo(const telefonata& t, nodo* s) : info(t), next(s) {};
bolletta::bolletta(): first(nullptr) {};
bool bolletta::Vuota() const {
    return first == nullptr;
};
void bolletta::Aggiungi_Tel(const telefonata& t){
    first = new nodo(t, first); //aggiunto alla lista
};
void bolletta::Togli_Tel(const telefonata& t){
    nodo *p = first, *prec = nullptr;
    while(p && !(p->info == t)){ // continuo a cercare finchè non trovo una telefonata = t 
                                 // o finchè p!= null
        prec = p;
        p = p->next;
    }
    if(p){
        if(prec==nullptr)
            first = p->next;
        else
            prec->next=p->next; // rimozione logica
        delete p; //rimozione cella di memoria 
    }
};
telefonata bolletta::get_Una(const telefonata& t){ // bolletta non vuota
    nodo* p=first;
    first = first->next;
    telefonata tmp = p->info; // costruzione di copia
    delete p;
    return tmp;
};
```

#### Interferenza/Aliasing
Viene causata da:
1. Condivizione di memoria
2. Funzioni con side effects
L'**aliasing** è una situazione in cui la locazione di un dato in memoria ci si può accedere da diversi nomi simbolici. Modificando il dato con un nome modifica il valore associato a tutti gli *alias*, che non ci si aspetta.

###### Shallow Copy
È eseguita dall'assegnazione standard e dal costruttore di copia standard. Viene copiato il valore di A in B, se modifichi l'indirizzo di memoria a cui punta B, modifichi anche dove punta A.

###### Deep Copy
È un'alternativa alla **shallow copy** dove i dati sono effettivamente sovrascritti, dove A e B non dipendono l'uno dall'altro.


### Lifetime
Il **tempo di vita** di un oggetto è il tempo tra la creazione e la sua distruzione. In generale il tempo di vita di un oggetto non per forza è legato al tempo di vita di una variabile.

#### Variabile Statica
È una variabile che viene allocata **staticamente**, il suo *lifetime* dura per tutta l'esecuzione del programma. Si trovano nella **memoria statica**.

Le ***variabili dinamiche*** sono nell'**heap**.

### Distruttore
Un **distructor** è un metodo che viene invocato automaticamente quando un oggetto viene distrutto. Il **distruttore standard** distrugge tutti campi di dati della classe in ordine inverso alla loro dichiarazione.
```c++
bolletta::~bolletta() {distruggi(first);} 
// distrugge la lista in modo ricorsivo e di conseguenza anche la bolletta
```

I *distruttori* vengono invocati:
- per oggetti **statici**, al termine del programma
- per oggetti definiti in un blocco, all'uscita dal blocco in cui sono dichiarati
- per oggetti **dinamici**, quando viene invocato `delete` su un puntatore ad essi
- per oggetti che sono *campi dati* di un oggetto `x`, quando `x` viene distrutto
- per oggetti con lo stesso tempo di vita, sono distrutti in ordine inverso a quello in cui sono creati

Il distruttore viene invocato, in particolare, nell'ordine:
1. sulle *variabili locali* di una funzione, quando si esce dalla funzione
2. sull'*oggetto anonimo* ritornato per valore da una funzione, non appena esso è stato usato
3. sui *parametri* di una funzione, all'uscita dalla funzione

##### Regola del Tre
È una regola, che se una classe definisce uno o più tra *distruttori*, *costruttori di copia*, *operatore di assagnazione di copia*, allora bisogna probabilmente definire esplicitamente tutte e tre.

### Dichiarazioni incomplete
Una classe `C` può dichiarare ed usare puntatori e reference ad una classe `D` che viene meramente dichiarata. È una **dichiarazione incompleta** della classe `D`.

#### Funzione Amica
È un metodo *amico* di una data classe e può accedere ai dati privati e protetti. Queste funzioni vanno usate con attenzione. Troppe dichiarazioni di amicizia possono creare dei problemi.

```c++
class bolletta{
    friend ostream& operator<<(ostream&, const bolletta&);
};
```

#### Overloading operatori puntatore
```c++
telefonata* operator->() const {return &(punt->info);};
telefonata& operator*() const {return punt->info;};
```
