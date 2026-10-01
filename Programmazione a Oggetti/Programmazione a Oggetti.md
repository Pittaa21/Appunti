## Caratteristiche del linguaggio C++
- Compilato
- Tipizzazione forte statica (*strongly typed*)
- No garbage collector
- Standardizzato (C++17, C++20 in progress)
- General-purpose e molto diffuso (Adobe, Mozilla, MySQL, Microsoft, Chromium, giochi…)
- Efficienza
- Supporto all’overloading degli operatori
- Ampia libreria standard

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
![[carbon(5).svg]]

### Metodi inline
Se definiti direttamente dentro la classe, i metodi sono **inline**:
![[carbon(7).svg]]
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

## Information Hiding
> **Definizione:** principio di segregazione delle decisioni progettuali che hanno maggiori probabilità di cambiare, proteggendo il resto del programma da modifiche estese.

- Si realizza fornendo un’**interfaccia stabile** che nasconde l’implementazione.
- Impedisce l’accesso a certi aspetti di una classe tramite `private` o policy di esportazione.
- Parte **pubblica** = interfaccia (documentazione).
- Parte **privata** = implementazione nascosta.
- Dall’esterno si accede solo alla parte pubblica.
- I metodi della classe possono accedere alla parte privata di *qualsiasi* oggetto della classe (non solo di quello di invocazione).

## ADT – Abstract Data Type
> **Definizione:** tipo di dato le cui istanze possono essere manipulate esclusivamente tramite la semantica del dato, non dalla sua implementazione.

- Distinzione netta tra:
  - **Interfaccia**: operazioni fornite (metodi pubblici)
  - **Implementazione interna**: modo in cui lo stato è conservato e le operazioni manipolano i dati
- L’inaccessibilità dell’implementazione è detta **incapsulamento** o **information hiding**.
- ADT = **Valori + operazioni**.
- Esempio di ADT primitivo: `int`.
- `struct` del C/C++ non rispetta il concetto di ADT (membri pubblici di default).

## Namespace
> **Definizione:** meccanismo che permette di incapsulare nomi che altrimenti inquinerebbero il namespace globale. Non è disponibile in C.

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

### Stringhe in STL
- `string` è una classe della libreria standard STL.
- È un’istanza di un template: `typedef basic_string<char> string`.
- Esempio d’uso:
```cpp
string st1;        // costruttore: stringa vuota
string st2(st);    // costruttore di copia
cout << st.size(); // metodo size()
```

### Esempio di ADT: Numeri Complessi
- **Rappresentazione cartesiana:** `struct comp { double re, im; };`
- Operazioni tipiche: `inizializzaComp`, `reale`, `immag`, `somma`.
- **Rappresentazione polare:** modulo `mod` e argomento `arg`.
  - `mod = sqrt(r*r + i*i)`
  - `arg = atan(i/r)`
  - `reale() { return mod*cos(arg); }`
  - `immag() { return mod*sin(arg); }`
- La classe nasconde la rappresentazione interna e fornisce un’interfaccia pubblica.

## Compilatore
- `g++` è l’alias per `gcc -xc++`.
- Su macOS `g++` è in realtà `clang` (frontend per LLVM).
- Ultima versione GCC: 14.2 (Luglio 2024).
