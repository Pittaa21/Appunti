**MS-DOS** (*Microsoft Disk Operating System*): in modalità linea di comando, singolo utente, non *multi-programmato*

**Windows** di 1° generazione ha una **GUI** solo come rivestimento di **MS-DOS**.

**GUI** (*Graphical User Interface*): realizzabile come programma (*linux*) o come parte del S/O (*windows*)

**Windows** di 2° generazione è *multiprogrammato* e utilizza **FAT**.

**Windows** di 3° generazione progetto *NT* e abbandono della base **MS-DOS**, architettura a 16 bit. Nuovo *File system* **ntfs**.

Tutte le informazioni di configurazione del sistama sono raccolte in un File System detto *registry* salvato in file detti *hives*.

***Job***: più processi gestiti come una singola unità con limiti di risorse.
***Processo***: più di un *thread*.
***Thread***: flusso di controllo gestito dal nucleo.
***Fiber***: suddivisione di *thread* sconosciuta al nucleo.

## Thread
I ***thread*** si sincronizzano in vari modi:
- *semafori* binari o contatori
- *sezioni critiche* limitate dallo spazio di indirizzamento del *thread*

I ***thread*** comunicano senza sincronizzazione tramite:
- *Pipe*: canali bidirezionali come in UNIX
- *Socket*: come le pipe ma per comunicazioni remote, quindi due macchine diverse
- *Mailslot*: canale unidirezionale

**Ordinamento con prerilascio a priorità**: da azioni esplicite del *thread*, nessuna entità attiva dedicata di sistema.

6 classi di priorità per processo.
**realtime, high, above-normal, normal, below-natural, idle**
7 classi di priorità per *thread*.
**time-critical, highest, above-normal, normal, below-normal, lowest, idle**
32 livelli di priorità (31 ... 0)

Ciascun *thread* ha una priorità base iniziale e una corrente che varia nel corso dell'esecuzione. La **priorità** aumenta quando: il *thread* completa un'operazione di I/O, ottiene un semaforo o riceve un segnale d'evento. La **priorità** diminuisce a ogni *quanto di tempo*.

Per evitare il problema di ==inversione di priorità==: un *thread* pronto che non viene selezionato per un certo tempo riceve un aumento di **priorità** per 2 quanti di tempo.

## Gestione Memoria
Ogni **processo** ha uno spazio di indirizzamento **virtuale paginato** ampio 4GB e diviso in 2 zone adiacenti di ampiezza 2GB ognuna. Gli *indirizzi virtuali* sono espressi da 32 bit.

Un *pagina virtuale* può essere: **R** (lettura) / **W** (scrittura) / **E** (esecuzione).
- **Libera**: non riferita da alcun **PTE** (*Page Table Entry*), tutte le pagine di un processo sono inzialmente libere
- **Assegnata**: in uso per codice o dati, riferita tramite indirizzo virtuale e caricata da disco se non presente in RAM
- **Prenotata**: non ancora in uso, ma ==non libera==, quando si crea un nuovo processo 1MB è riservato allo stack.

Più processi possono condividere l'accesso alle pagine di un *file* **mappato in memoria**, un esempio è la libreria ==DLL==.

La stessa posizione del *file* può corrispondere ad **indizzi virtuali** diversi per **processi** diversi.

Il caricamento in RAM di una pagina nuova può necessitare il ***rimpiazzo*** locale di una pagina *vecchia*:
- se non ci sono abbastanza pagine libere
- se il sistema mantiene una lista di pagine libere
- a ogni processo $i$ si associa l'insieme l$_{i}$ delle sue pagine che si trovano in RAM (*Working Set*)

Si ha un ***rimpiazzo globale*** se e solo se un processo deve scambiare le proprie pagine tra RAM e disco troppo spesso.

Anche il S/O è visto come un **processo** con un proprio **WS** con pagine rimpiazzabili, alcune pagine però sono **inamovibili**.
Un ***deamon*** del *Kernel* accerta che ci sono sufficienti pagine libere, se insufficienti il ***deamon*** attiva un ***thread*** del ==Memory manager== che esamina i **WS** dei processi per rilasciarne pagine.

Ciascuna *page frame* in RAM può essere:
- In uso e appartenere a 1 **WS** o più se condivisa
- **Rilasciata** e appartenere a 1 sola lista tra:
    - ***A*** In attesa: ossia recentemente rimossa dal **WS** di un processo ma ancora ==associata== e ==non modificata==
    - ***B*** Da copiare su disco: come ***A*** ma se rimpiazzata deve essere riportata su disco
    - ***C*** Libera: come ***A*** ma ==non associata== ad alcun processo
    - ***D*** Azzerata: come ***C*** ma con il contenuto annullato a zero per consentire che il precedente contenuto non possa essere estrapolato, in modo malevolo
    - ***E*** Difettosa: non può essere usata a causa di ==difetti nella zona della memoria fisica==

Lo stato della RAM è mantenuto in una **tabella** dedicata a cui si accede per indice di **pagina fisica** (*page frame database*)
C'è un *deamon* (**swapper thread**) del **Memory manager** mette in ***A*** o ***B*** le pagine dello *stack* dei processi i cui *thread* sono stati inattivi di recente.
Altri 2 *deamon* si assicurano che ci sono abbastanza pagine in ***C*** salvando su disco quelle in ***B*** e accodandole in ***A***.
Un **Working Set** che cresce  preleva le pagine libere da ***C*** se le sovrascrive interamente, altrimenti da ***D***.

## NTFS
***NTFS*** è il *file system* adottato da **Windows NT** e poi **XP** e **Vista**. Supporta tutti i FS Windows e anche ***ext2fs*** di **GNU/Linux**. 
Gli indici sono espressi su 64 bit.

### Architettura NTFS
- Nome dei *file* fino a 255 caratteri in **UNICODE**
- *File* inteso come **insieme di attributi** rappresentati come ==sequenza di caratteri== (*byte stream*)
- Ha un'***architettura gerarchica*** (come *ext2*):
    - usa \ invece che / come separatore nelle espressioni di cammino
    - supporta entrambe le forme di *link*

**NTFS** è una collezione di **volumi logici**: un volume logico può mappare su più partizioni e su più dischi.
Per ***volume*** si intende una sequenza **lineare di blocchi** (*cluster*) di ampiezza fissa, volumi diversi possono avere dimensioni di blocco diverse. Con blocchi piccoli la ***frammentazione interna*** è ridotta, mentre con quelli più grandi si hanno ==meno accessi== al disco ma più ***frammentazione***.

##### MFT
La struttura principale dei dati è ***MFT*** (*Master File Table*):
- Una per **volume**
- Realizzata ==fisicamente== come un *file*
- Strutturata ==logicamente== come una **sequenza lineare** di *record* di ampiezza da 1 a 4 KB

Ciascun *record* ha un numero variabile di coppie: `<descrittore attributo, valore>`:
- 1° campo specifica la **struttura** dell'attributo
- 2° campo indica il **valore** dell'attributo: ==residente== (24B) se rappresentato interamente dal *record* o ==non residente== se rappresentato da un puntatore ($\geq$ 24B)
Il valore dell'attributo **dati** è il contenuto effettivo del *file*.

##### Assegnazione
**NTFS** cerca di assegnare allo stesso *file* sequenze di ==blocchi contigui== invece che blocchi singoli isolati (come **ext2fs**). Se non è possibile i dati si trovano su sequenze di blocchi singoli ==non adiacenti==. Esiste un *record* base in **MFT** per ogni *file sequenziale* presente nel volume.

##### Rappresentazione
L'***NTFS*** permette di rappresentare *file* di ampiezza virtualmente ==illimitata==. Il numero di *record* necessari ai dati di 1 singolo *file* dipende dalla **contiguità** dei suoi blocchi piuttosto che dalla sua ampiezza.

La rappresentazione di *file* può necessitare di più *record*, **NTFS** usa una tecnica a **continuazioni** analoga a quella degli *i-node* di **UNIX** e **GNU/Linux**. Ossia il *record base* in MFT contiene un puntatore a N *record* secondari in MFT che descrivono la sequenza di blocchi del *file*.
Se non c'è sufficiente spazio per i *record* secondari, la loro lista viene trattata come un **attributo non residente** e messa in un *file* dedicato indicato da un *record* in MFT.