## Protocollo
> **Definizione**: i protocolli definisco il formato, l'ordine dei messaggi inviati e ricevuti e le azioni da prendere quando si riceve o trasmette

## Layers
- Modello **OSI**: (Open System Interconnection) composto da *Upper layers* per le applicazioni e *lower layers* per le comunicazioni:
    1. Physical: manda/riceve bits sul media fisico
    2. Data Link: incapsulazione per la trassmissione e rilevamento errori
    3. Network: consegna i pacchetti (*routing*)
    4. Transport: trasferisce i dati tra processi
    5. Session: stabilisce sessioni di comunicazione a livello *applicativo*
    6. Presentation: i dati sono rappresentati in formato adatto per macchine diverse (*encrypting*)
    7. Application: gestisce la rete

- Modello **TCP/IP**

Si usa un modello **ibrido** che ha:
1. Physical Layer
2. Data link Layer
3. Network Layer
4. Transport Layer
5. Application Layer


==Multiplexing==: simulare più canali usando un solo canale di comunicazione (*multitasking*)

==Routing==: più di un modo per mandare un messaggio

---
### Cavi
**Bandwidth**: *capacità* del canale, larghezza di banda. La misura dell'ampiezza di una porzione dello spettro dei segnali.

- Cavo coassiale: schermatura migliore degli UTP, bandwidth di circa 1 GHz
- Twisted Pair: coppia annodata, l'intreccio serve a limitare l'interferenza reciproca
    - UTP3: bandwidth di circa 250 MHz
    - UTP5: bandwidth di circa 600 MHz

##### Fibra ottica
Usata per trasmissioni a lunga portata, è immune ai disturbi elettrici e alle condizioni atmosferiche e poco sensibile alla variazione di temperatura. Hanno dei raggi di luce al loro interno con differenti angoli, si usa il principio di riflessione totale interna. Bandwidth migliore.

---
### Wireless

##### Spettro Elettromagnetico
Il numero di *oscillazioni* per secondo di un'onda, elettromagnetica di elettroni, è la ***frequenza*** $f$ misurata in HZ. La distanza tra due *massime* o *minime* consecutive è la ***lunghezza d'onda*** $\lambda$.

Quando un'antenna viene attaccata ad un circuito elettrico, le onde elettromagnetiche possono essere *catturate* da un ricevitore. Su questa idea si basano le **comunicazioni wireless**.

##### Trasmissione Radio
Le **frequenze radio** (*Radio Frequency* RF) sono onde facili da generare, possono attraversare lunghe distanze e penetrare le strutture facilmente, sono quindi ampiamente usate nella **comunicazione**, *interna* e *esterna*. Inoltre, sono **omnidirezionali**, quindi il trasmettitore e il ricevitore non devono essere perfettamente allineati.

Le onde radio a **bassa frequenza** come *AM*, si disperdono facilmente.
Mentre quelle ad **alta frequenza**, non attraversano bene gli ostacoli e sono assorbite dalla pioggia.

##### Trasmissione a micro-onde
Sopra i 100MHz, le onde viaggiano quasi in linea retta, possono essere meglio *focalizzate* e percorrere distanze più lunghe, ma ricevitore e trasmettitore devono essere meglio allineati. Prima della fibra ottica, le **micro-onde** erano il centro delle comunicazioni a lunga distanza.
Le **micro-onde** sono **direzionali** e sono necessari dei *ripetitori*.
Non possono attraversare efficaciemente gli ostacoli, e sono soggette a delle *interferenze atmosferiche* come il **multipath fading**.

##### Trasmissioni Infrarossi
Usate per comunicazioni a corto raggio (telecomandi). Sono **direzionali**, economiche e sicure


#### DSL
Una *linea* di *telecomunicazioni digitale*, hanno velocità di 56KB, con i modem è quasi il **limite fisico**

##### ADSL
Uso di 256 sottocanali: 1 per la *voce*, 32 per l'*upstream*, 5 *vuoti* e il resto per il *downstream*. Usano l'ampiezza del canale voce (4312.5 Hz).
Ciò viene fatto per evitare che l'interferenza su un canale influenzi tutto il *downstream* o *upstream*. Ogni sottocanale è trattato come una connessione a sè.
Vari tipi:
- **ADSL Lite**: 1.5Mbit/s download, 0.5Mbps upload
- **ADSL**: 8Mbit/s download, 1Mbps upload
- **ADSL2**: 12Mbit/s download, 1Mbps upload
- **ADSL2+**: 24Mbit/s download, 1Mbps upload
Le **ADSL2+** usano una *banda doppia* ossia 2.2Mhz

Per maggiore velocità ci si basa sull'utilizzo della fibra.

##### xDSL
- **VDSL**: Very high-speed DSL. Simile all'ADSL, ma si usano frequenze più alte. 55Mb download, 3Mb upload
- **VDSL2**: 200Mb download, 100Mb upload
- **VDSL2+**: 300Mb download, 100Mb upload

Si basano sulla qualità del cavo e da quanto ce nè.

Per decidere il rapporto tra *download* e *upload* si usano dei **piani di banda**.


##### FTTH
Fiber to the home, niente più cavo in rame UTP3, ma la fibra:
- **GPON**: 2.5Gb download, 1.2Gb upload
- **XGPON**: 10Gb download, 2.5Gb upload
Le caratteristiche di queste due tecnologie sono **totali**.
Questa è per ogni collegamento:
- **NG-PON2**: 10Gb download/upload, meno usata in Italia

### Multiplexing
Viene usato per l'ADSL, per il telefono e Internet, per dividere la frequenza.

Nel caso dei telefoni su un singolo cavo si possono tenere fino a 600 conversazioni contemporaneamente, tramite un terzo livello di suddivisione (***mastergroup***)

#### FDM
multiplexing in frequenza

#### WDM
Nel caso della fibra ottica si usa la *Wavelenght DM*, quindi tramite dei *combiner* e *splitter* si combinano e separano i fasci di luce usando il concetto del prisma. Si tratta di una tecnologia completamente **passiva**, non necessitano di corrente elettrica, sono quindi più affidabili, veloci e duraturi.

#### TDM
multiplexing temporale. Oltre a dividere i canali si divide anche il tempo.
Viene usato nella fibra ottica, musica, 

##### Televisione
Può avere trasmissione **satellitare** e **digitale**.
Il digitale terrestre usa **QAM** nelle varianti: QAM-4, QAM-16, QAM-64.
Il satellite usa **QPSK**. 

C'è il problema degli *echi* del terreno. Per risolvere il problema si usa il **FDM** allo stesso modo dell'ADSL. 
Ogni canale è suddiviso in tante trasmissioni indipendenti in due modi:
- **2K**: 1705 sottocanali
- **8K**: 6817 sottocanali

##### Switching
La struttura della rete telefonica (*PSTN*), il suo traffico è gestito da dei *switching center* in tre modi:
- **circuit switching**: viene creato un **collegamento fisico** (circuito elettrico) tra due utenti. È per i collegamenti fisici serve del tempo, c'è quindi un *delay* iniziale.
- **message switching**: invece di creare il percorso e poi iniziare la trasmissione, il messaggio viene inviato subito, così facendo appena il percorso è finito il messaggio arriva subito, diminuito il *delay* iniziale, problema dei messaggi grandi (**sostituito**)
- **packet switching**: quando si ha un messaggio grosso,viene diviso in *packets* di lunghezza massima nota. Viene resa possibile la trasmissione in parallelo.

### Telefonia Mobile
#### 0G (Gen Zero)
Deriva dalla trasmissione radio: **PTT** ossia **Push To Talk**, un solo canale per ricevere o trasmettere, **half-duplex**, ossia *push* per trasmettere senza ricevere.

#### IMTS (Improved Mobile Telephone System)
Si passa a due frequenze, niente PTT. Viene introdotto un livello di **privacy**: non si sentono le comunicazioni degli altri. Si usano dei *super-trasmettitori* ad alta potenza, ci sono solo 23 canali per centinaia di km per *cella* che evita le interferenze.

#### 1G
Viene introdotto **AMPS** (**Advanced Mobile Phone System**), in Italia *TACS*. Ora le *celle* sono molto più piccole (10-20km). Aumenta la **capacità** degli utenti che usano il servizio e diminuisce la **potenza** richiesta per la trasmissione, quindi meno uso della batteria dei telefoni. 
C'è il problema dell'**interferenza** tra celle: si usa la *separazione di frequenza*. Il numero di frequenze dipende dalle *zone*, dalla *densità* d'uso, e dalla necessità di *espansione*, solitamente si usano 3 o 7 frequenze.

Ogni **cella** ha al centro lo *switching center*, un cellulare è connesso ad una sola cella, finchè non si sposta. Si deve trovare il modo di passare il segnale ad un'altra cella