# STU-01 · Consultare il materiale didattico

**Ruolo:** Studente (ARC-003)

**Storia**

Come Studente, voglio consultare il materiale didattico caricato dai docenti della mia classe, diviso per materia, per poter studiare quando e dove voglio: dall'iPad a scuola, dal PC o dal telefono a casa.

---

## Acceptance criteria della traccia

> 💡 Riportare qui gli AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Materiale diviso per materia**
Dato che sono autenticato come Studente e iscritto a una classe, quando apro la sezione Materiale, allora vedo l'elenco delle materie della mia classe e, per ognuna, quanti materiali ci sono.

**AC-02 · Elenco dei materiali di una materia**
Dato che ho scelto una materia, quando consulto i materiali, allora li vedo ordinati dal più recente, con titolo, descrizione, docente, data di caricamento e tipo (file o link), in un elenco paginato.

**AC-03 · Aprire un file**
Dato che sto guardando un materiale caricato come file, quando lo apro, allora il file viene scaricato o aperto dal browser del dispositivo, con il suo nome originale.

**AC-04 · Aprire un link** *(collegato alla proposta DOC-01 AC-06)*
Dato che sto guardando un materiale caricato come link, quando lo apro, allora la pagina si apre in una nuova scheda, senza farmi uscire da ScuolaChill.

**AC-05 · Solo il materiale della mia classe**
Dato che sono autenticato come Studente, quando consulto i materiali, allora vedo solo quelli caricati per la mia classe. Se provo ad aprire il materiale di un'altra classe, anche chiamando direttamente l'API o usando il link diretto al file, il sistema rifiuta la richiesta con errore di autorizzazione.

**AC-06 · Materiale nuovo**
Dato che un docente ha caricato un materiale dopo il mio ultimo accesso, quando apro la sezione Materiale, allora quel materiale è segnato come "nuovo" e la materia mostra quanti materiali nuovi contiene *(proposta, da confermare)*.

**AC-07 · Ricerca**
Dato che cerco un materiale preciso, quando scrivo una parola nella ricerca, allora vedo i materiali della mia classe il cui titolo o descrizione la contengono, in tutte le materie o solo in quella scelta.

**AC-08 · Usabile da iPad, PC e smartphone** *(NFR-11)*
Dato che apro ScuolaChill dall'iPad a scuola, oppure dal PC o dal telefono a casa, quando consulto materie e materiali, allora la pagina si adatta allo schermo, si usa con il touch e posso aprire un materiale senza zoomare né scorrere in orizzontale.

**AC-09 · Nessun materiale**
Dato che i docenti di una materia non hanno ancora caricato nulla, quando la apro, allora vedo un messaggio che lo dice, non una pagina vuota.

**AC-10 · Studente senza classe**
Dato che il Direttore non mi ha ancora assegnato a una classe (DIR-02 AC-04), quando apro la sezione Materiale, allora vedo un messaggio che mi spiega che non sono ancora in una classe, non un errore.

**AC-11 · Materiale modificato o eliminato**
Dato che un docente ha modificato o eliminato un materiale (DOC-01 AC-08, AC-09), quando ricarico l'elenco, allora vedo la versione aggiornata, oppure il materiale non c'è più. Se apro un materiale eliminato da un link salvato, vedo un messaggio che non è più disponibile.

**AC-12 · File non disponibile**
Dato che lo storage dei file non risponde, quando provo ad aprire un materiale, allora vedo un messaggio che il file al momento non è raggiungibile e posso riprovare; il resto dell'elenco continua a funzionare.

**AC-13 · Cambio di classe** *(proposta, da confermare)*
Dato che il Direttore mi ha trasferito in un'altra classe (DIR-04 AC-08), quando apro la sezione Materiale, allora vedo il materiale della nuova classe e non più quello della classe precedente.

**AC-14 · Sola lettura**
Dato che sono autenticato come Studente, quando consulto il materiale, allora non posso caricarlo, modificarlo né eliminarlo (DOC-01 AC-13).

---

## Regole e dati

| Dato mostrato | Regola |
| --- | --- |
| Materia | Solo le materie della classe dello studente (DIR-04) |
| Titolo, descrizione | Come inseriti dal docente (DOC-01) |
| Docente | Nome e cognome di chi ha caricato il materiale |
| Data di caricamento | Data e ora, formato italiano |
| Tipo | File (con formato ed estensione, es. PDF) o link |
| Nuovo | Caricato dopo l'ultimo accesso dello studente *(proposta)* |

- Lo studente vede il materiale della coppia classe/materia, non del docente: se il docente cambia, il materiale resta visibile (DOC-01 AC-12).
- Il file si scarica con un link temporaneo che vale solo per lo studente che lo ha chiesto: copiare il link e passarlo a uno studente di un'altra classe non funziona (AC-05).
- Ordine di grandezza: con 412 studenti che consultano il materiale più volte al giorno, è l'operazione di lettura più frequente dopo il login.

## Fuori perimetro di questa storia

- Caricamento, modifica ed eliminazione del materiale → **DOC-01**
- Anteprima dei file dentro ScuolaChill (il file si apre con il browser o con l'app del dispositivo)
- Cartelle o argomenti per organizzare il materiale *(da decidere insieme a DOC-01)*
- Notifiche allo studente quando arriva materiale nuovo *(da decidere)*
- Uso offline del materiale già scaricato

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| NFR | NFR-02 | HTTPS: i file viaggiano cifrati |
| NFR | NFR-03 | Controllo ruolo e classe lato backend, anche sul download dei file (AC-05) |
| NFR | NFR-09 | Elenco materiali paginato (AC-02) ed errori uniformi (AC-05, AC-11, AC-12) |
| NFR | NFR-11 | Usabile da iPad, PC e smartphone (AC-08) |
| Storia | DOC-01 | Il materiale consultato qui è quello caricato dal docente |
| Storia | DIR-02 | Studente creato senza classe (AC-10) |
| Storia | DIR-04 | Classi, materie e trasferimento dello studente (AC-01, AC-13) |

## Domande aperte per il team

1. Dopo un trasferimento lo studente deve vedere ancora il materiale della classe precedente (AC-13)? *(proposta: no, solo quello della classe nuova)*
2. Il segno "nuovo" (AC-06) vi serve? Richiede di salvare l'ultimo accesso di ogni studente.
3. Il Direttore e i docenti di altre materie della stessa classe possono consultare il materiale come lo studente?
