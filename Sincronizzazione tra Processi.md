I processi **indipendenti** possono avanzare *concorrentemente* senza alcun vincolo di ordinamento. Molti processi condividono risorse e informazioni funzionali, per gestire tale condivisione servono dei meccanismi di **sincronizzazione di accesso**.

Prendiamo come esempio i processi **A** e **B** che condividono la risorsa **X** = 10.
- **A** incrementa **X** di 2
- **B** decrementa **X** di 4
**A** e **B** leggono *concorrentemente* **X**:
- **A** legge che **X** è 10 e viene *prerilasciato* prima di poter eseguire la propria istruzione, quindi anche **B** legge 10
- successivamente i due processi eseguono le proprie operazioni su **X**, in *concorrenza*, non considerando l'operazione svolta dall'altro processo
- quindi **X$_A$** vale 12  e  **X$_B$** vale 6
Il valore finale di **X** è l'ultimo che viene scritto tra **X$_A$** e **X$_B$**  (12 o 6) invece di 8.

**Race Condition**: il risultato dell'esecuzione dipende da *temporizzazione* o dall'ordine in cui si eseguono le istruzioni.

**Sezione Critica**: parte di codice che limita l'accesso a una risorsa condivisa tra processi in un sistema *concorrente*.

La modalità di accesso *indivisa* a una risorsa condivisa è detta **mutua esclusione**. Si utilizza una variabile logica (*lock*) che indica se la risorsa condivisa è in uso (**mutex**).

```java
// A e B devono accedere a X ma prima ne verificano lo stato
if (lock == 0){
	// X è in uso
}else{
	// X è libera
	lock = 0;
	// uso della risorsa e poi liberata
	lock = 1;
}

```

Questa soluzione è inadeguata poichè:
- i due processi possono essere *prerilasciati* dopo aver letto *lock* ma prima di aver modificato la risorsa
- l'algoritmo richiede **attesa attiva** che spreca tempo di CPU
**Attesa attiva**: attesa che continua a verificare se avviene un cambio di valore, occupando inutilmente il processore.

Una soluzione è:
1. Garantire **accesso esclusivo**
2. Garantire **attesa finita**
3. non fare **assunzioni** sull'ambiente di esecuzione
4. Non subire condizionamenti dai processi esterni alla *sezione critica*

Esempio:
```java
Processo (int i){
	while(True){
		IN(i);
		//sezione critica
		OUT(i);
		// altro
	}
}

IN(int i){
	int j = (1 - i); // l'altro processo
	flag[i] = True;
	turn = i;
	while(flag[j] && turn == i){
		// attesa attiva
	};
}

OUT(int i){
	flag[i] ) False;
}
```
Considerando due processi **P(0)** e **P(1)**.
Si suppone che venga eseguito prima  **P(0)** che vedrà *i* = 0 e *j* = 1  quindi *flag*[0] = 1
Si suppone che adesso **P(0)** venga prerilasciato prima di modificare la variabile *turn* e va in esecuzione **P(1)** che vede *i* = 1 e *j* = 0, quindi *flag*[1] = 1 infine *turn* = 1 quindi impostato su se stesso. Se adesso si prerilascia anche **P(1)** e torna in esecuzione **P(0)** (continua l'esecuzione precedente). *turn* = 0 la condizione del *while* è verificata **P(0)** va in **attesa attiva** (fino al prossimo prerilascio). Quando **P(0)** viene prerilasciato, **P(1)** non soddisfa il *while* e va nella **sezione critica** gestita in **mutua esclusione**. Se **P(1)** viene di nuovo prerilasciato **P(0)** si trova ancora in **attesa attiva** e potrà andare nella *sezione critica* solo quando **P(1)** finisce la propria *sezione critica* ossia quando chiama la funzione *OUT* e pone *flag*[1] = *False*.


Alternative:
- **Disabilitare le interruzioni**: previene il *prerilascio* per esaurimento di tempo o la promozione di processi a priorità più elevata. Inutilizzabili per processi con *interruzioni* frequenti
- **Test and Set Lock**: cambia automaticamente *lock* se segnala "libero", evita situazioni di *race condition* ma comporta *attesa attiva*

Queste soluzioni hanno il problema della *attesa attiva*, inoltre può verificarsi l'**inversion priority**, ossia quando il processo a priorità alta (H) viene *prerilasciato* per eseguire I/O e quando lo conclude il processo a bassa priorità (L) si trova in *sezione critica*. In questo caso H rimane bloccato in *attesa attiva* perchè L non ha modo di finire la sua *sezione critica*.

### Produttore-Consumatore
```java
const int N = 100;
int count = 0;

void producer(void){
	int item;
	while(True){
		item = produce_item();    // genera il prossimo item
		if(count == N)            // se il buffer è pieno, dormi
			sleep();
		insert_item(item);        // inserisce item nel buffer
		count++;                 
		if(count == 1)            // se il buffer è vuoto sveglia il consumatore
			wakeup(consumer);
	}
}

void consumer(void){
	int item;
	while(True){
		if(count == 0)             // se il buffer è vuoto, dormi
			sleep();
		item = remove_item();      // rimuove l'item dal buffer
		count--;
		if(count == N - 1)         // se il buffer è pieno sveglia il produttore
			wakeup(producer);
		consume_item(item);        // stampa l'item
	}
}
```

**Rischio Race condition** su variabile *count*:
Si verifica quando il buffer è vuoto e il **consumer** ha appena letto che *count* = 0. Prima che il **consumer** vada in sleep, lo *scheduler* ferma il **consumer** ed esegue il **producer**. Il **producer** produce un *item* e mette *count* = 1. Siccome *count* = 1 **producer** emette wakeup (non ascoltato). Lo *scheduler* decide di rieseguire **consumer** che inizia lo *sleep*, ma visto che *count* è già impostato a 1 la *wakeup* è già stata fatta, quindi il **consumer** non verrà più risvegliato.

## Semafori
Una soluzione al problema è tramite l'utilizzo di un **semaforo**, il quale:
- Richiede accesso *indiviso*(**atomico**) alla variabile di controllo denominata *semaforo*
	- **Semaforo** *binario*: contatore Booleano 0 o 1
	- **Semaforo** *contatore*: permette tanti accessi in contemporanea, in base a quanto vale il contatore
- La richiesta di accesso **P**, decrementa il contatore se non si trova già a 0, altrimenti va nella coda di **attesa** (*wait*)
- Il rilasco **V**, incrementa il contatore e chiede al *dispatcher* di mettere in **pronto** il primo processo in coda (*signal*)

```java
void Processo(){

	P(sem);   // viene invocata P per richiedere l'accesso alla risorsa condivisa R
	// uso di una risorsa condivisa R
	V(sem);   // viene invocata V per rilasciare la risorsa R
}
```

Tramite l'utilizzo di **semafori** *binari* si possono **coordinare** più processi per l'esecuzione di attività collaborative.

```java
void ProcessoA(){
	// esecuzione indipendente
	P(sem); // in attesa di B
	// seconda parte della collaborazione
}

void ProcessoB(){
	// prima parte della collaborazione
	V(sem); // rilascio di A
	// esecuzione indipendente
}
```

Il **semaforo** *binario* (*mutex*) è una struttura (*struct*) composta da un campo valore intero e un campo coda che contiene tutti i *Process Control Block* dei processi in attesa. L'accesso al campo valore avviene in maniera **atomica**.

Il **semaforo** *contatore* ha la stessa struttura del **mutex** ma ha logica diversa per il campo lavoro: se maggiore di 0 la disponibilità non è esaurita, se minore ci sono richieste pendenti.
Il valore iniziale determina la capacità massima della risorsa.

#### Problemi Semafori
L'uso dei semafori a livello di programma è *rischioso*:
- Il posizionamento errato di **P** può portare a blocchi infiniti (*deadlock*) o esecuzioni sbagliate di difficile verifica (*race condition*)
- Non bisognerebbe lasciare il pieno controllo all'utente

## Monitor
Il **monitor** definisce la *regione critica*, il compilatore inserisce il codice necessario al controllo degli accessi.
Un **monitor** è un insieme di sottoprogrammi, variabili e *struct*. Solo i sottoprogrammi del **monitor** possono accedere alle sue variabili. Un solo processo per volta può essere attivo nel **monitor**.
Viene garantita la *mutua esclusione* 