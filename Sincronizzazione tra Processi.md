I processi **indipendenti** possono avanzare *concorrentemente* senza alcun vincolo di ordinamento. Molti processi condividono risorse e informazioni funzionali, per gestire tale condivisione servono dei meccanismi di **sincronizzazione di accesso**.

Prendiamo come esempio i processi **A** e **B** che condividono la risorsa **X** = 10.
- **A** incrementa **X** di 2
- **B** decrementa **X** di 4
**A** e **B** leggono *concorrentemente* **X**:
- **A** legge che **X** è 10 e viene *prerilasciato* prima di poter eseguire la propria istruzione, quindi anche **B** legge 10
- successivamente i due processi eseguono le proprie operazioni su **X**, in *concorrenza*, non considerando l'operazione svolta dall'altro processo
- quindi **X$_A$** vale 12  e  **X$_B$** vale 6
Il valore finale di **X** è l'ultimo che viene scritto tra **X$_A$** e **X$_B$**  (12 o 6) invece di 8.