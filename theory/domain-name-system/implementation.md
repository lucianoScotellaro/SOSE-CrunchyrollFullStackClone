## Implementation

This file presents the implementation process, and choices, used to implement the authoritative DNS server at [src/content-subsys/authoritative-dns](../../src/content-subsys/authoritative-dns/)

### Non-Functional Requirements

Al momento per un server authoritative ho individuato tre principali non-functional requirements:

1. Security
2. Performance
3. Lightness

Alla luce di questi tre requisiti non funzionali il server dovrebbe essere scritto in C in quanto:

1.
2. Compilato e non interpretato, meno overhead per lavorare su byte raw (lavora direttamente in memoria) mentre Python richiede delle conversioni, e ogni elemento non è un oggetto il che non richiede l'esistenza di un garbage collector che aggiunge overhead.
3. Non richiede il caricamento in memoria di una VM per interpretare il programma, ma solo il binario compilato che è molto più leggero. Inoltre non richiede l'esistenza di un interprete sulla macchina target.

Tuttavia per ora lo sviluppo in Python per concentrarmi sul protocollo e poi vedrò quanto è complesso tradurlo.

### Creating the UDP server

An authoritative server is a server communicating through the DNS protocol, and serves the authoritative level IP resolution.

_Controlla definizione non sono sicuro. Me la sono inventata sul momento._

In the DNS protocol the communication with the client is handled via the usage of UDP on the port 53.

This means that the **first step** needed to implement a custom authoritative server is to **create** a **UDP server** that listens on **port 53**.

To do this the **first step** is to **create** a **UDP socket**. In Python we can do this as follows.

_Perché la prima cosa da fare per creare un server è creare una socket? Cos'è una socket concretamente?_

Senza la socket che fa il binding traffico-programma il server non esiste. Per questo la prima cosa da fare è creare la socket.

_Perché usiamo UDP? Quali sono le differenze con TCP? Perché in questo caso è meglio UDP?_

```python
import socket

bla bla bla
```

With the socket created, the **next** step is to **bind** it to the **port 53** of the **host** machine, so that ...