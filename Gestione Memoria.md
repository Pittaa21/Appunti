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

La tabella delle pagine serve alla MMU (*hardware*), il caricamento della pagina da disco è a 

#### Segmentazione
- **Programma**: è una collezione di *segmenti*
- **Segmento**: è un'unità logica come: *main*, *funzioni*

Un processo si può dividere o in *pagine* o in *segmenti* che non hanno bisogno di essere allocati in modo contiguo in memoria, durante l'esecuzione non tutte le *pagine* o *segmenti* devono essere caricati in memoria centrale.

Più processi possono stare in memoria principale, è quindi più probabile ci siano più processi *ready*. Inoltre un processo può essere più grande della memoria principale.

La **memoria reale** è quella principale. La **memoria virtuale** è invece quella sul disco e rende facile la *multiprogrammazione* e libera l'utente dalle limitazioni della memoria principale.

