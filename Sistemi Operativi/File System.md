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