- **MS-DOS** (*Microsoft Disk Operating System*): in modalità linea di comando, singolo utente, non *multi-programmato*

**Windows** di 1° generazione ha una **GUI** solo come rivestimento di **MS-DOS**.

- **GUI** (*Graphical User Interface*): realizzabile come programma (*linux*) o come parte del S/O (*windows*)

**Windows** di 2° generazione è *multiprogrammato* e utilizza **FAT**.

**Windows** di 3° generazione progetto *NT* e abbandono della base **MS-DOS**, architettura a 16 bit. Nuovo *File system* **ntfs**.

Tutte le informazioni di configurazione del sistama sono raccolte in un File System detto *registry* salvato in file detti *hives*.

**Job**: più processi gestiti come una singola unità con limiti di risorse.
**Processo**: più di un *thread*.
**Thread**: flusso di controllo gestito dal nucleo.
**Fiber**: suddivisione di *thread* sconosciuta al nucleo.

### Thread
I **thread** si sincronizzano in vari modi:
- *semafori* binari o contatori
- *sezioni critiche* limitate dallo spazio di indirizzamento del *thread*

I **thread** comunicano senza sincronizzazione tramite:
- *Pipe*: canali bidirezionali come in UNIX
- *Socket*: come le pipe ma per comunicazioni remote, quindi due macchine diverse
- *Mailslot*: canale unidirezionale

**Ordinamento con prerilascio a priorità**: da azioni esplicite del *thread*, nessuna entità attiva dedicata di sistema.

6 classi di priorità per processo.
**realtime, high, above-normal, normal, below-natural, idle**
7 classi di priorità per *thread*.
**time-critical, highest, above-normal, normal, below-normal, lowest, idle**
32 livelli di priorità (31 ... 0)

TABELLA

Ciascun *thread* ha una priorità base iniziale e una corrente che varia nel corso dell'esecuzione