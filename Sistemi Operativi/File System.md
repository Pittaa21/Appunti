###### File:
Insieme di dati correlati, residenti in **memoria secondaria** e trattati unitariamente.

Il ***file system*** (FS)  designa la parte di S/O che si occupa di *file* secondo:
- Organizzazione
- Gestione
- Realizzazione
- Accesso

##### Problemi 
- Cosa offrire all'utente applicativo e in che forma:
    - Modalità accesso ai *file*
    - Struttura logica e fisica dei *file*
    - Operazioni ammissibili sui *file*
- come realizzarlo in modo pratico ed economico

### File
Il ***file*** è un concetto logico realizzato mediante **meccanismi di astrazione**, ossia:
- Salvare le informazioni in memoria e poterle ritrovare in seguito senza sapere la stuttura logico-fisica e il funzionamento, all'utente non interessa come si verificano questi passaggi
- All'utente interessa poter assegnare le proprie unità di informazione con **nomi logici** *unici* e *distinti*. Infatti l'utente vede e tratta solo nomi di *file*
- Le caratteristiche che distinguono un *file* sono:
    - **Attributi** tra cui:
        - *Nome*: stringa da 8 a 255 caratteri (numeri e speciali) con almeno 1 estensione per determinare il *tipo* di file
        - *Dimensione corrente*
        - *Data creazione*
        - *Data ultima modifica*
        - *Creatore e possessore*
        - *Permessi di accesso*: lettura scrittura, esecuzione<br>
    - **Struttura interna** considerata in 3 punti:
        1. Livello *utente*: il programma applicativo associa significato al **contenuto grezzo** del *file*
        2. Livello *struttura logica*: il S/O organizza i dati grezzi in strutture logiche per facilitarne il trattamento
        3. Livello *struttura fisica*: il S/O mappa le strutture logiche sulle strutture fisiche in memoria secondaria disponibile<br>
    - **Operazioni ammesse**

###### Strutture logiche
Le possibile strutture logiche di un *file* sono:
- Sequenza di *byte* (*byte stream*): metodo più rudimentale e flessibile (scelto da **UNIX** e **MS Windows**), il *programma applicativo* sa come dare significato al contenuto del *file*, si usa un puntatore relativo all'inizio del *file*, infine lettura e scrittura sono a **blocchi di byte**. Si ha quindi lo sforzo minimo del S/O.<br>
- *Record* di lunghezza e struttura *fissa*: il S/O deve conoscere la struttura interna del *file*, gli spazi non usati sono riempiti da `NULL` o `SPACE`. L'accesso ai dati è sequenziale e si usa un puntatore al *record* attuale. La lettura e scrittura operano sui singoli *record*.<br>
- *Record* di lunghezza e struttura *variabile*: La struttura interna di ogni *record* viene descritta e identificata univocamente da una *key*, che sono raccolte in una tabella contenente anche i puntatori all'inizio di ogni *record*. L'accesso ai dati è per *chiave*. Si usa nei *mainframe*.

#### Modilità di accesso
- Accesso **sequenzale**: un gruppo di *byte* (o *record*) alla volta. Un puntatore indirizza il *record* corrente e avanza a ogni lettura e scrittura. La lettura può essere in qualsiasi posizione, mentre la scrittura è solo in coda. Sul *file* si opera solo sequenzialmente.<br>
- Accesso **diretto**: opera su *record* di dati posti **arbitrariamente** nel *file*.<br>
- Accesso **indicizzato**: per ogni *file* una tabella di *chiavi* ordinate che contengono gli *offeset* dei *record*. Si ha una ricerca binaria della *chiave* o poi **accesso diretto**.

### Classificazione
Il FS può trattare diversi tipi di *file*:
- **File regolari**: dove l'utente può operare normalmente, contenuto testuale (ASCII) o eseguibile (binario)
- **File catalogo** (*directory*): usati dal FS per descrivere l'organizzazione di gruppi di *file*
- **File speciali**: usati dal FS per rappresentare logicamente dispositivi orientati a carattere (*terminale*) o blocco (*disco*)

### Operazioni
- **Creazione**: *file* inizialmente vuoto
- **Apertura**: precede il primo utilizzo e predispone le informazioni utili per l'accesso
- **Cerca posizione** (*seek*)
- **Cambia nome** (*rename*)
- **Distribuzione**: rilascio della memoria occupata
- **Chiusura**: rilascio delle strutture di controllo usate per accesso e salvataggio dati
- **Lettura** e **Scrittura** (*read*, *write*, *append*)
- **Trova attributi**
- **Modifica attributi**

Le azioni più complesse si ottiene tramite la combinazione delle operazioni base.

#### File mappati in memoria
Il S/O può mappare un *file* in memoria virtuale.
Il *file* continua a risiedere in memoria secondaria, all'indirizzo di ogni suo dati si ha un indirizzo di memoria virtuale (base + *offset*). Le operazioni su *file* avvengono in memoria principale. A fine sessione tutte le modifiche fatte in memoria primaria sono riportate in quella secondaria.

### Struttura directory
Ogni FS  usa *directory* o *folder* per tener traccia dei sui *file regolari*. Le *directory* possono essere classificate secondo l'organizzazione dei *file* che contengono:
- **A livello singolo**: tutti i *file* elencati su un'unica lista lineare (*root directory*), quindi è facile trovare i *file*
- **A due livelli**: una *root directory* contiene una *User File Directory* per ciascun utente, *file* localizzati tramite un ==percorso== (*path name*)
- Ad **albero**: numero di livelli arbitrario, quello superiore è la *root*, ogni *directory* può avere *file* regolari o *directory*, il cammino può essere ==assoluto== rispetto alla radice del FS, oppure ==relativo== rispetto alla posizione attuale
- A **grafo aperto**: come ad albero però lo stesso *file* appartiene a più *directory*, su **UNIX** e **GNU/Linux** si usano collegamenti simbolici tra nome reale del *file* e la presenza virtuale
- A **grafo generalizzato** (con *cicli*): sono possibili i riferimenti circolari

Requisiti fondamentali a livello utente:
- **Efficienza**: semplice realizzare un *file* e facile e veloce trovarlo
- **Libertà di denominazione**: più utenti possono usare lo stesso nome per un *file* proprio che può essere chiamato in modo diverso da utenti diversi
- **Libertà di raggruppamento**: creare gruppi logici di *file* sulla basi di proprietà dell'utente


- ***Hard Link***: Un puntatore diretto a un *file regolare* viene inserito in una *directory* ad esso remota, ci sono così 2 vie distinte di accesso al *file*

- ***Symbolic (Soft) Link***: Si crea un *file speciale* che contiene il cammino del *file* originario, si ha 1 sola via di accesso al *file* originario

