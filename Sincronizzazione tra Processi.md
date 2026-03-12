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

