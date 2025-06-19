# SO2-clientserver

**Progetto client-server multithread in C** per il corso di **Sistemi Operativi II** – Università La Sapienza.

Il progetto implementa un server TCP multicliente, in grado di gestire richieste da parte di client concorrenti, supportando operazioni sui file (scrittura e lettura) con varie modalità.

---

## Compilazione

Per compilare i tre componenti principali:

```bash
# Compilazione file funzioni condivise
gcc -Wall -o funzioni_condivise.o -c funzioni_condivise.c

# Server
gcc -Wall -o server server.c funzioni_condivise.o -lpthread

# Client
gcc -Wall -o client client.c funzioni_condivise.o

--- 
## Esecuzione

./server -a <indirizzo_ip> -p <porta> -d <directory>
-a: indirizzo IP su cui ascoltare (es: 127.0.0.1)
-p: numero di porta (es: 8080)
-d: directory in cui leggere/scrivere i file gestiti

## Comandi client
Il client può inviare due tipi principali di richieste al server:

-W (scrittura file sul server) -> Permette di inviare un file al server.
-R (richiesta di lettura file dal server) -> Scarica un file dal server.


## Funzionalità
1) Server TCP multi-thread
2) Supporto a più client concorrenti
3) Invio file dal client al server (-W)
4) Download file dal server (-R)
5) Supporto percorsi relativi e assoluti
6) Possibilità di specificare nome output (opzione -o)
7) Gestione directory di lavoro lato server

