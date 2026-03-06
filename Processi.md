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

#### Transizioni




### Stallo
Si verifica quando:
- Accesso esclusivo a delle risorse condivise
- Accumulazione di nuove risorse
- Una risorsa deve essere rilasciata volontariamente (*Inibizione di Prerilascio*)
- Attesa circolare, cioè un processo attende la risorsa posseduta dal processo successivo

#### Prevenzione Stallo
