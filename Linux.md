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

Permanentemente in RAM e per tutti i processi ci sono:
- Parametri di ordinamento (priorità, tempo di esecuzione, tempo di sospensione, ...)
- Descrittore della memoria virtuale del processo
- Lista dei segnali significativi e il loro stato
- Stato, identità, relazioni di parentela, gruppo di appartenenza

```c
while(True){
    type_prompt(); // mostra il prompt sullo schermo
    read_command(cmd, par); // legge linea di comando
    pid = fork();
    if(pid < 0){
        printf("Errore di attivazione del processo");
        continue; // si ripete il ciclo
    };
    if(pid != 0){
        // codice eseguito dal padre
        waitpid(-1, &status, 0); // attende la terminazione di un figlio
    }else{
        // codice eseguito dal figlio
        execve(cmd, par, 0); 
    };
};
```

All'istruzione `pid = fork()` il processo che chiama al Kernel e inserisce i dati per il figlio nella **tabella dei processi**. Se ci riesce viene allocata la memoria per lo *stack* e i dati del figlio. A questo punto il codice del figlio è lo stesso del padre.

Con il comando `execve(cmd, par, 0)` la linea di comando emessa dall'utente viene passata al processo figlio come *array* di stringhe. La *exec*, che opera nel Kernel, trova il programma da eseguire e lo sostituisce al codice del chiamante.

IMG

**fork()**