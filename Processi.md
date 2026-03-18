Un **Processo** è un *programma in esecuzione* che ha:
1. un insieme *ordinato* di *stati* assunti durante l'esecuzione
2. un insieme *ordinato* delle *azione* svolte dal programma durante l'esecuzione

#### Caratteristiche
- esistono processi utente e di S/O che possono cooperare ma possiedono privilegi diversi
- i processi avanzano *concorrentemente*, a cui il S/O assegna le risorse in base a *priorità* o divisione di *tempo*
- i processi devono comunicare e *sincronizzarsi* tra loro
- un processo può creare dei sottoprocessi *figli* 
- i processi vengono:
	- **Creati** per svolgere un lavoro
	- **Sospesi** per poter eseguire altri processi
	- **Terminati** una volta completato il lavoro

#### Gestore dei Processi
Il **Kernel** è la parte centrale del S/O, gestisce:
- L'avanzamento dei processi
	- lo *scheduling*, ossia la scelta del processo da eseguire in un certo istante
	- il cambio di stato dei processi
- Le interruzioni esterne
	- eventi di I/O
	- anomalie rilevate da altri processi
- Permette ai processi di accedere alle risorse di sistema e attendere
- La Politica di ordinamento deve essere equa (*fair*)
	- i processi pronti devono poter essere eseguiti
	- i processi che attendono le risorse devono poter accederci
- La comunicazione e sincronizzazione deve essere efficacie

### Risorsa
La **Risorsa** è un elemento fisico (*hardware*) o logico (*software*) necessario per la creazione, esecuzione e avanzamento dei processi.
- **Risorsa CPU**: a livello fisico corrisponde alla CPU, a livello logico si può vedere come una "*macchina virtuale*" 
- **Risorsa Memoria**: accesso individuale per la *scrittura*, accesso multiplo per la *lettura*, viene *virtualizzata* per renderla riutilizzabile e prerilasciabile
- **Risorsa I/O**: riutilizzabili, ma non prerilasciabili e ad accesso *individuale*. L'accesso fisico ha bisogno del *BIOS*

### Stati
- **Disattivato**: il programma si trova nella memoria secondaria e viene caricato in memoria tramite una chiamata di sistema che crea un *Process Control Block*, **PCB** ossia una struttura di controllo del processo
- **Pronto**: il processo resta in attesa del suo turno, ha tutte le risorse tranne il processore
- **Esecuzione**: al processo viene attribuito il processore, può essere eseguito
- **Attesa**: Il processo è in attesa di una risorsa o un evento
- **Terminato**: il processo ha finito le sue operazioni e abbandona la *macchina virtuale*

#### Strutture di Rappresentazione
**Process Table**: modello di processo realizzato tramite una tabella (*Array di strutture*).
Ogni processo è rappresentato da un **Process Control Block** che contiene:
- Identificatore del processo
- Contesto di esecuzione del processo
- Stato di avanzamento del processo
- Priorità
- Privilegi e diritti di accesso alle risorse
- Puntatore al **PCB** del processo genitore e i figli
- Puntatore alla lista delle risorse assegnate al processo
- ...

#### Ordinamento di Processi
Metodi per determinare quando sostituire un processo in esecuzione con un altro (*switch*).
- **Scambio cooperativo**: il processo in exec. decide quando cedere il controllo al processo successivo
- **Scambio a prerilascio**: il precesso in exec. viene sostituito da un processo con priorità maggiore o all'esaurimento del suo lasso di tempo

#### Dispatcher
**Dispatcher**: è il componente che avvia processi all'esecuzione (ma non li seleziona: *scheduler*).
I processi in stato *pronto* sono messi nella code de la *ready list*. La più semplice gestione della lista è **Fist-Come-First-Served** (*FCFS*):
- il primo processo ad entrare nella lista è il primo ad essere eseguito

Solitamente un processo possiede alcune azioni eseguibili dalla CPU alternate da azioni di I/O. Ci sono quindi due classificazioni:
1. Processi **CPU-bound**: attività sulla CPU con durata molto lunga
2. Processi **I/O-bound**: attività brevi sulla CPU, con attività di I/O molto lunghe

*FCFS* penalizza i processi **I/O-bound**.
Suddividento il tempo sulla politica *FCFS* si ottiene una tecnica di rotazione **Round Robin**.

| A   | B$_1$ | c$_1$ | B$_2$ | C$_2$ | B$_3$ | C$_3$ | C$_4$ | C$_5$ |
| --- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |

Politica a **rotazione con priorità**: a ogni processo si attribuisce una *priorità* che denota il llivello di privilegio nel sistema. I processi si possono categorizzare (**CPU-bound**, **I/O-bound**)

[[Sincronizzazione tra Processi]]