Sistema **multi-programmato** e **multi-utente**.
L'architetture è a *livelli gerarchici*.

![[linux(1).svg|center]]

**UNIX** nasce con una interfaccia utente per linea di comando (*shell*), è quindi più potente e flessibile di una **GUI** ma per utenti esperti. Si ha una *schell* per ogni terminale utente (*xterm*):
- caratteri di *prompt* (%, $): indicano dove modificare il comando
- *pipe*: comando composto che prende l'output di comandi e l'utilizza come input di altri (tramite |)
- i comandi possono essere inviati all'esecuzioni liberando la *shell* (&, *background*)

## Gestione dei Processi
Un **Processo** è la principale entità attiva nel sistema, inizialmente *sequenziale*. Si verifica della concorrenza tra processi: molti processi vengono attivati dal sistema (*daemon*). I processi figli hanno memoria identica a quella del processo genitore (all'inizio), poi alla prima modifica diventa *indipendente*.

### Thread
*Processi* con più flussi di controllo interni sono detti **thread**. I *thread* condividono tutte le risorse logiche e fisiche del processo genitore (inclusi i valori delle variabili). Una volta che completa il proprio lavoro il *thread* termina se stesso volontariamente. Un *thread* si può sincronizzare con la terminazione di un suo simile, l'accesso a risorse condivise si sincronizza tramite **semafori** a *mutua esclusione*. L'attesa su condizioni logiche avviene con variabili speciali simili a *condition variables* (ma senza monitor).

