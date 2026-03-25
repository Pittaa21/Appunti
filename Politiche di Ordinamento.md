Ogni processo è associato a un *descrittore*: il **Process Control Block** che specifica:
- Identificatore processo
- Contesto di esecuzione
- Stato di avanzamento: puntatore alla lista di processi in un determinato *stato*
- Priorità
- Diritto di accesso a risorse e privilegi
- *Discendenza familiare*: puntatore al **PCB** del processo genitore
- Puntatore alla lista di risorse assegnate al processo
### Stati di avanzamento dei Processi

![[stati.svg|center|496]]

Ci sono vari metodi per decidere come alternare i vari processi in esecuzione:
- **Scambio Cooperativo**: il processo in esecuzione decide quando cedere il controllo
- **Scambio a Prerilascio**: il processo in esecuzione viene rimpiazzato da uno con priorità più alta o al termine del quanto di tempo

Il prerilascio è realizzato tramite un meccanismo *esterno* all'esecuzione, ossia tramite un dispositivo che provoca una interruzione, un gestore la identifica e la notifica allo *scheduler*. 

Lo **scheduler** è il componente del *kernel* che decide l'ordinamento dei processi. Il suo operato deve essere **parametrico** rispetto agli attributi assegnati ai processi.

Il **dispatcher** è il componente del *kernel* che esegue le scelte di ordinamento dei processi, opera su ordine dello *scheduler*, inoltre deve essere molto efficiente poichè opera a ogni scambio di contesto.

L'efficienza delle politiche di ordinamento si misura in:
- Percentuale di impiego della CPU
- Numero di processi avviati in esecuzione
- Durata di permanenza di un processo pronto
- Tempo di completamento
- Reattività alla richiesta di avvio di un processo
La *garanzia* di esecuzione dei processi dipende dalla *politica* di scambio adottata.

I processi in stato *pronto* sono registrati in una **lista dei pronti**. La più semplice gestione di questa lista è tramite la coda (**First-Come-First-Served**, **FCFS**) ossia il primo processo che entra in code è il primo ad essere eseguito. Applicando una divisione di tempo (**time sharing**) sulla politica **FCFS** si ottiene una tecnica di rotazione **round-robin**. Tramite il *round-robin* se si hanno per esempio tre processi, in 3 quanti di tempo diversi: per *T1* viene eseguito un pezzo del processo *P1*, per *T2* si esegue un pezzo di *P2* e lo stesso per *T3* si esegue *P3*, e così via fino a terminare tutti e 3 i processi.

| A   | B$_1$ | c$_1$ | B$_2$ | C$_2$ | B$_3$ | C$_3$ | C$_4$ | C$_5$ |
| --- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
Politica a **rotazione con priorità**: a ogni processo si attribuisce una *priorità* che denota il llivello di privilegio nel sistema. I processi si possono categorizzare (**CPU-bound**, **I/O-bound**)

I meccanismi per realizzare scelte di ordinamento e gestione risiedono nel *kernel*. Le politiche invece sono determinate al di fuori di esso.
Diverse classi di sistemi concorrenti richiedono politiche
di ordinamento di processi specifiche:
- **Sistemi a lotti** (*batch*): ordinamento predeterminato, per lavori di lunga durata e urgenza limitata, non necessita prerilascio
- **Sistemi interattivi**: grande varietà di attività, prerilascio necessario
- **Sistemi in tempo reale**: lavori di durata ridotta ma elevata urgenza, l'ordinamento riflette l'importanza del processo, possibile il prerilascio

Caratteristiche delle politiche di ordinamento:
1. **Equità** (*fairness*): nella distribuzione delle opportunità di essere eseguiti
2. **Coerenza** (*enforcement*): ossia applicare la politica a tutti i processi
3. **Bilanciamento**: nell'uso di tutte le risorse di sistema

#### Sistemi a lotti
- **FCFS**: senza prerilascio, ordine di esecuzione è l'ordine di arrivo, massima semplicità e basso utilizzo di risorse
- **SJF** (*Shortest Job First*): senza prerilascio, esegue per primo il lavoro più breve, non è equo con i lavori non presenti all'inizio
- **SRTN** (*Shortest Remaining Time Next*): variante di **SJF** con prerilascio, esegue per primo il processo più veloce da completare, tiene conto dei nuovi processi quando arrivano
Si parla di *lavori* quando non c'è il prerilascio e di *processi* quando il prerilascio è presente.

#### Sistemi interattivi
- **OQ** (*ordinamento a quanti*): con prerilascio, senza priorità, ogni processo esegue al più per un quanto alla volta, lista circolare dei processi
- **OQP**: *ordinamento a quanti con priorità*, quanti diversi per livello di priorità
- **GP** (*Garanzia per processo*): con prerilascio e con promessa di una data quantità di tempo di esecuzione (*1/n* per *n* processi concorrenti), esegue prima il lavoro più penalizzato rispetto alla promessa
- **SG** (*Senza Garanzia*): con prerilascio e priorità, più alta è la priorità più numeri ha quel processo e periodicamente vengono estratti dei numeri che decide il processo da eseguire
- **GU** (*garanzia utente*): come **GP** ma con garanzia riferita a ciascun utente

#### Sistemi in tempo reale
Sono sistemi *concorrenti* dove il valore corretto deve essere prodotto entro un tempo fissato, oltre tale limite il valore prodotto ha utilità decrescente, nulla o negativa. L'ordinamento (*scheduling*) dei processi deve fornire garanzie di completamento adeguate.