## Grafo di Assegnazione delle Risorse
Si considerano due processi **P1**, **P2** e 2 tipi di risorse **R1**, **R2** con disponibilità: 1 risorsa di tipo **R1** e 1 di tipo **R2**.
##### Cronologia di Richieste
1. **P2** richiede **R1**
2. **P1** richiede **R2**
3. **P2** richiede **R2**
4. **P1** richiede **R1**
Bisogna verificare se il sistema si trova in *stallo*.
Il *Grafo di allocazione delle risorse* è il seguente:
![[GrafoAsRis1.svg|center|280]]
Visto che si è formato un ciclo il sistema è in **stallo**.
