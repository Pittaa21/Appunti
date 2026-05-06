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