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

## File
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


I *file system* sono memorizzati su disco, il quale può essere **partizionato** e ogni partizione può avere un FS diverso. Il settore 0 del disco ha le informazioni di inizializzazione del sistema: *Master Boot Record* (*MBR*) che ha una descrizione delle partizioni e identifica quella attiva. Il primo blocco di ogni partizioni ha le sue informazioni specifiche di inizializzazione, *boot block*. L'**inizializzazione** è eseguita dal ***BIOS***.

A livello fisico un *file* è un insieme di blocchi di disco, bisogna decidere quali blocchi assegnare e come tenerne traccia. Ci sono quindi 3 modi di allocazione di blocchi a *file*:

- **Allocazione contigua**: si cerca di memorizzare i *file* su blocchi **consecutivi**, ogni *file* è descritto dall'indirizzo del suo primo blocco e dal numero di blocchi usati. Consente sia accesso **sequenziale** sia **diretto**. Le modifiche ai *file* comportano il rischio di ==frammentazione esterna==. <br>
- **Allocazione a lista concatenata** (*linked list*): *file* come lista concatenata di blocchi e identificato dal puntatore al suo primo blocco. Ogni blocco di *file* contiene il puntatore al prossimo blocco o alla fine della lista. L'accesso sequenzale è semplica ma ha bisogno di molte operazioni su disco. Un solo blocco guasto ==corrompe== l'intero *file*. <br>
- **Allocazione a lista indicizzata**: i puntatori ai blocchi sono in strutture apposite, i blocchi hanno solo i dati. Il *file* + descritto dall'insieme dei suoi puntatori. Si può organizzare in **forma tabulare** (***FAT***, *File Allocation Table*) o in **forma indicizzata** (***i-node***). Niente ==frammentazione esterna==. Consente accesso sequenziale e diretto, inoltre non serve sapere la dimensione massima del *file*.

### File Allocation Table (FAT)
Si usava in **MS Windows**.
Si tratta di una *tabella ordinata di puntatori*, si ha un puntatore per ogni blocco (*cluster*), quindi la tabella aumenta con l'ampiezza della partizione. La porzione di **FAT** relativa ai *file* in uso deve stare sempre interamente in RAM. Un *file* è una catena di indici.

*Esempio*: Con un disco da 200GB, blocchi da 1KB, serve FAT da 200 milioni di righe ognuna di 3-4 Bytes: 600-800MB di memoria usati.

#### Nodi indice (i-node)
Si usano in **UNIX**, **GNU/LINUX**.
Si ha una struttura indice (**i-node**) per ogni *file*. L'*i-node* ha gli attributi del *file* e i puntatori ai blocchi del file. L'*i-node* si trova in un blocco dedicato. In RAM si ha una tabella di *i-node* solo per i *file* in uso, la dimensione massima della tabella dipende dal numero massimo di *file* apribili in contemporanea.

Un *i-node* ha un numero limitato di puntatori a blocchi. Per i *file* di piccola dimensione gli indirizzi dei blocchi dei dati sono contenuti in un singolo *i-node*. Per dimensioni maggiori, un campo dell'*i-node* principale punta a un livello di blocchi di *i-node* intermedi che puntano ai blocchi di dati. Se non ancora sufficiente si aggiungono altri livelli.


##### Gestione file condivisi
Per ogni *file* condiviso si mette nella *directory* remota un *symbolic link* verso l'originale, così esiste un solo un *i-node*. L'accesso condivisio avviene per cammino sul FS. Oppure nella *directory* remota si può mettere il puntatore diretto (*hard-link*) al descrittore (*i-node*) del *file* originale. Il ==proprietario== del *file* è unico. Il *file* condiviso non può essere distrutto finchè esistono dei suoi descrittori remoti.

##### Gestione blocchi liberi
- Vettore di *bit* (*bitmap*) dove ogni *bit* indica lo stato del blocco: 0 libero, 1 occupato
- Lista concatenata di blocchi: scelta da **FAT**.

### MS-DOS (Microsoft Disk Operating System)
Non è ***multiprogrammato***, quindi l'utente vede tutto il FS. Il FS è **gerarchico** senza limite di profondità e senza condivisione. Le *directory* hanno lunghezza variabile con *entry* di 32 B. Allocazione *file* a lista: **FAT**.

- **FAT-X** per **X**: numero di *bit* per indirizzo di blocco 12 $\leq$ **X** $<$ 32
    - **Blocchi/Cluster** di dimensione multipla di 512 B
- **FAT-16**: *file* e partizione limitati a 2 GB
- **FAT-32**: indirizzi da 28 *bit*, perchè Win95 ha come limite di partizione 2TB quindi $\text{2}^{28}\cdot\text{2}^{13}=\text{2}^{41}$B $=$ 2TB. Dimensione di blocchi in questo caso da 8 KB.


### Integrità FS
- **Consistenza FS**: Un *file* viene aperto, modificato e prima di essere salvato il sistema cade, il salvataggio del contenuto del *file* su disco è ==inconsistente==.
- **Consistenza blocchi**: 2 liste di blocchi con un contatore per ogni blocco: lista blocchi in uso dei *file*, lista blocchi liberi.
    - Ciascun blocco appartiene a una e sola lista ***consistenza***
    - un blocco non appartiene ad alcuna lista ***perdita***
    - il contatore del blocco è maggiore di 1 in una delle due liste ***duplicazione***

### Prestazioni FS
- Una porzione di memoria principale viene usata come *cahce* di blocchi, in questo modo si riduce la frequenza di accesso ai dischi, l'accesso ai blocchi avviene tramite ricerca *hash*.
- Occorre garantire la consistenza dei dati: **MS-DOS** i blocchi modificati son copiati subito su disco (*write trough*), **UNIX** un processo periodico *sync* effettua l'aggiornamento dei blocchi su disco.
