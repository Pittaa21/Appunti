La **memoria**, secondo gli utenti, deve essere *capiente*, *veloce* e *permanente*. 

Il **gestore della memoria** è la parte del S/O che soddisfa le esigenze di memoria dei processi.
La **memoria disponibile** è *minore* di quella necessaria a tutti i processi attivi in contemporanea.

##### Sistemi monoprogrammati
- si esegue un processo per volta
- la memoria è ripartita solo tra quel processo e il S/O

Vantaggioso per pochi processi.

### Frammentazione
Suddivisione in più parti della memoria

- **Interna**: la memoria è divisa in blocchi di grandezza *uguale*, comporta uno *spreco di memoria*
- **Esterna**: la memoria è divisa in blocchi di grandezza *variabile*, comporta un calo alle prestazioni del sistema

Nei sistemi **multiprogrammati** viene creata una partizione per ogni processo, il problema è quindi assegnare dinamicamente processi alle partizioni. A ogni nuovo *processo* si assegna la partizione di dimensione più adatta.
Poco efficacie nell'uso della memoria disponibile.

##### Rilocazione
Interpretazione degli indirizzi emessi da un processo in relazione alla sua collocazione corrente in memoria

##### Protezione
Assicurazione che ogni processo opera solo nello spazio di memoria a esso permesso.

#### Swapping
Tecnica per alternare processi in **memoria principale** senza garanzia di **allocazione fissa**. Bisogna prendere un processo per intero e salvarlo in memoria principale, non è possibile spezzarlo. Al processo si assegna partizioni diverse nel tempo.
Rischio di **frammentazione esterna**.


Avendo la memoria principale allocata dinamicamente bisogna tener traccia del suo stato d'uso. 
Due strategie:
1. **Mappe di bit**
2. **Liste collegate**

Strategie di allocazione:
- **first fit**: primo segmento libero ampio a sufficienza
- **next fit**: come *first fit* ma cercando sempre verso avanti
- **best fit**: segmento libero più adatto
- **worst fit**: segmento libero più ampio
- **quick fit**: liste diverse di ricerca per ampiezze *tipiche*

## Memoria Virtuale
Una singola partizione o l'intera RAM sono insufficienti per un'intero processo. La prima soluzione è stata dividere il processo in parti (*overlay*) che venivano caricate in RAM una parte per volta.

L'idea di **memoria virtuale** si basa sul fatto che un singolo processo può avere ampiezza maggiore della RAM disponibile. Basta caricare solo la parte strettamente necessaria e lasciare il restante sul disco.
Quindi ogni processo ha il proprio spazio di *memoria virtuale*.

Gli *indirizzi generati* dalla CPU, quindi non linkano direttamente alla RAM ma sono **indirizzi virtuali** (*logici*), che vengono interpretati dalla **MMU** che li trasforma in indirizzi *fisici reali*.

#### Paginazione
- **Memoria fisica**: è divisa in blocchi di dimensione fissa (*page frame*)
- **Memoria virtuale**: è divisa in blocchi della stessa dimensione (*pagine*)

I trasferimenti da e verso il disco avvengono sempre in **pagine**. Di ogni **pagina** bisogna sapere se è presente in RAM, tramite *bit di presenza*. Se una pagina manca quando avviene il riferimento si genera un **page fault**, evento gestito dal S/O tramite *trap*.

La traduzione da *virtuale* a *fisico* avviene con una **tabella delle pagine**, di cui ciascun processo ha la propria. 

La traduzione deve esere molto veloce, infatti un'istruzione può fare riferimento più volte alla stessa tabella; quindi il suo **rifermento** deve metterci meno del tempo totale di esecuzione dell'istruzione per evitare *bottleneck*. Ogni indirizzo emesso dal processo deve essere tradotto.

La **tabella delle pagine** serve alla **MMU** (*hardware*), il caricamento della pagina da disco è a carico del S/O (*software*) quando si verifica un **page fault**.
La **tabella delle pagine** è talmente grande che non può stare nei registri, quindi sta in RAM, per migliorare le prestazioni si usa una sorta di *cache*: **HW**. Il *translation lookaside buffer* (**TLB**) è una piccola *memoria associativa* che permette la scansione parallela e si trova all'interno della **MMU**. Ogni indirizzo emesso verso **MMU** viene prima trattato con **TLB**. Se la pagina è presente e l'accesso è permesso la *traduzione* avviene con **TLB**; altrimenti si ha l'equivalente di un *cache miss* e le informazioni devono essere caricate in **TLB** dalla *tabella delle pagine*. Prevalentemente le **TLB** sono realizzate via *software*.

##### Problema:
Con architetture a 64 bit le *tabelle delle pagine* hanno dimensioni esagerate.

Tramite una **tabella invertita** non si ha più una riga per *pagina*, ma per *page frame* in RAM. Si risparmia così spazio ma la traduzione è più complessa.

##### Rimpiazzo
Quando avviene un *page fault* il S/O deve **rimpiazzare** una pagina, ma salvandola su disco se modificata. Non bisognerebbe **rimpiazzare** pagine ad uso frequente. 
Si usa quindi un **rimpiazzo ottimale** (*optimal replacement*), ossia si rimpiazza la pagina che non viene usata per maggior tempo.

- **NRU** (*Not Recently Used*): Per ogni *page frame* si aggiornano:
    - Bit M (*modified*) inizializzato a 0
    - Bit R (*referenced*) messo a 0 periodicamente per stimare la frequenza d'uso
    Le pagine sono classificate in:
    - **Classe 0**: non riferita, non modificata
    - **Classe 1**: non riferita, modificata
    - **Classe 2**: riferita, non modificata
    - **Classe 3**: riferita, modificata
    **NRU** sceglie una pagina a caso della classe non vuota di indice più basso.
- **FIFO**: Rimuove la pagine di ingresso più vecchio in RAM
- **Second Chance**: Corregge *FIFO* rimpiazzando solo le pagine con bit R = 0
- **Orologio**: Come SC ma i *page frame* sono mantenuti in una **lista circolare**
- **LRU** (*Least Recently Used*): Approssima l'algoritmo ottimale, necessita una lista aggiornata ad ogni riferimento a memoria
- **NFU** (*Not Frequently Used*): Per ogni *page frame* aggiorna periodicamente un *contatore* C che cresce di più se R = 1
- **Aging**: NFU modificato, approssima LRU con delle differenze

##### Working set
Il ***working set*** è l'insieme di *pagine* che un porcesso ha in uso a un dato istante, se la memoria non è sufficiente ad accogliere il *WS* si verifica il **thrashing**. Invece se il *WS* viene caricato prima dell'esecuzione si verifica il **prepaging**. Conoscere il *WS* dei processi a tempo d'esecuzione è una pratica ==troppo costosa==, anche se si avrebbe il vantaggio che le pagine da rimpiazzare sono quelle non comprese nel *WS*.

Si ha quindi un **WS approssimato**, simile all'*Aging*:
- Ogni *page frame* in RAM ha un attributo temporale che viene utilizzato insieme all'attributo riferito (R=1), questo attributo prende il tempo virtuale corrente all'arrivo di un *page fault*
- Al *page fault* sono rimpiazzabili le pagine con R=0 e valore dell'attributo precedente all'intervallo ($t-\Delta t,t$)

**WS approssimato** con **orologio**:
- *Page frame* organizzati in ==lista circolare==
- Una *lancetta* indica il *page frame* corrente, quando si verifica un *page fault* se R=1 la *lancetta* avanza e R=0
- Se nessun *page frame* è rimpiazzabile, si sceglie una pagina con M=0 oppure quella dove punta la *lancetta*

###### Anomalia di Belady
La frequenza di *page fault* non sempre descresce al crescere della grandezza della RAM.

**LRU** è immune all'*anomalia*. Gli ***stack algorithms*** sono immuni all'*anomalia di Belady*.

Nel rimpiazzare una pagina bisogna scegliere tra:

- Politiche ***locali***: viene rimpiazzato nel *WS* il processo che ha causato il *page fault*, ogni processo ha un tempo fisso in RAM. Hanno prestazioni **inferiori**, se *WS* di un processo cresce l'allocazione fissa provoca rimpiazzi indesiderati (*Thrashing*). Se il *WS* si riduce si ha uno spreco di memoria<br>
- Politiche ***globali***: scelti *page frame* senza distinzione di processo, allocazione in RAM varia dinamicamente nel tempo. Sono più **efficaci** soprattutto se l'ampiezza del *WS* varia durante l'esecuzione

Pagine **ampie** hanno un rischio maggiore di ***frammentazione interna***. Quelle **piccole**, invece, implicano un ampiezza maggiore della *tabella delle pagine*.

Quando si verifica un *page fault* il ***Program Counter*** dice a quale indirizzo si è verificato il problema


#### Segmentazione
- **Programma**: è una collezione di *segmenti*
- **Segmento**: è un'unità logica come: *main*, *funzioni*

Un processo si può dividere o in *pagine* o in *segmenti* che non hanno bisogno di essere allocati in modo contiguo in memoria, durante l'esecuzione non tutte le *pagine* o *segmenti* devono essere caricati in memoria centrale.

Più processi possono stare in memoria principale, è quindi più probabile ci siano più processi *ready*. Inoltre un processo può essere più grande della memoria principale.

La **memoria reale** è quella principale. La **memoria virtuale** è invece quella sul disco e rende facile la *multiprogrammazione* e libera l'utente dalle limitazioni della memoria principale.

