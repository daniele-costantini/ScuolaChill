# STU-04 · Consultare i compiti per casa

**Ruolo:** Studente (ARC-003)

**Storia**

Come Studente, voglio vedere sul registro i compiti per casa della mia classe, con la scadenza e il link per consegnarli su Classroom, per sapere cosa devo fare, entro quando e dove.

---

## Acceptance criteria della traccia

> 💡 Storia aggiunta dal team: la traccia non la prevede, quindi non ci sono AC della traccia da riportare.

## AC aggiunti dal team

**AC-01 · Elenco dei miei compiti**
Dato che sono autenticato come Studente e iscritto a una classe, quando apro la sezione Compiti, allora vedo i compiti della mia classe, di tutte le materie o di una sola, ordinati dalla scadenza più vicina, con materia, titolo e scadenza, in un elenco paginato.

**AC-02 · Dettaglio del compito**
Dato che apro un compito, quando lo leggo, allora vedo la descrizione, la scadenza, il docente e, se c'è, il link al compito su Classroom.

**AC-03 · Aprire il link**
Dato che il compito ha un link, quando lo apro, allora la pagina si apre in una nuova scheda, senza farmi uscire da ScuolaChill.

**AC-04 · Scadenza vicina**
Dato che un compito scade entro domani, quando apro la sezione Compiti, allora è messo in evidenza, non solo con il colore (per esempio con un'icona e la scritta "per domani").

**AC-05 · Compiti scaduti**
Dato che la scadenza di un compito è passata, quando apro la sezione Compiti, allora il compito non è più fra quelli da fare ma resta consultabile fra quelli passati.

**AC-06 · Compito nuovo** *(proposta, da confermare insieme a STU-01 AC-06)*
Dato che il docente ha segnato un compito dopo il mio ultimo accesso, quando apro la sezione Compiti, allora quel compito è segnato come "nuovo".

**AC-07 · Compito modificato o eliminato**
Dato che il docente ha modificato o eliminato un compito (DOC-04 AC-07, AC-08), quando ricarico l'elenco, allora vedo la versione aggiornata, segnata come "modificato", oppure il compito non c'è più.

**AC-08 · Nessun compito**
Dato che non ho compiti da fare, quando apro la sezione Compiti, allora vedo un messaggio che lo dice, non una pagina vuota.

**AC-09 · Studente senza classe**
Dato che il Direttore non mi ha ancora assegnato a una classe (DIR-02 AC-04), quando apro la sezione Compiti, allora vedo un messaggio che mi spiega che non sono ancora in una classe, non un errore.

**AC-10 · Usabile da iPad, PC e smartphone** *(NFR-11)*
Dato che apro i compiti dall'iPad a scuola, oppure dal PC o dal telefono a casa, quando li consulto, allora la pagina si adatta allo schermo e posso leggere i compiti e aprire i link senza zoomare né scorrere in orizzontale.

**AC-11 · Solo i compiti della mia classe**
Dato che sono autenticato come Studente, quando provo a vedere i compiti di un'altra classe (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

**AC-12 · Sola lettura**
Dato che sono autenticato come Studente, quando consulto i compiti, allora non posso segnarli, modificarli né consegnarli su ScuolaChill: la consegna avviene su Classroom (DOC-04 AC-05).

---

## Regole e dati

| Dato mostrato | Regola |
| --- | --- |
| Materia | Solo le materie della classe dello studente (DIR-04) |
| Titolo, descrizione | Come inseriti dal docente (DOC-04) |
| Scadenza | Data (e ora, se il docente l'ha indicata), formato italiano |
| Link | Se presente, si apre in una nuova scheda |
| Docente | Nome e cognome di chi ha segnato il compito |

- ScuolaChill non sa se lo studente ha consegnato: lo sa solo Classroom.
- Ordine di grandezza: lettura leggera, soprattutto il pomeriggio e la sera da casa.

## Fuori perimetro di questa storia

- Segnare, modificare ed eliminare i compiti → **DOC-04**
- Consegna e correzione: avvengono su Classroom o in classe
- Stato "consegnato" o "da consegnare" preso da Classroom
- Promemoria o notifiche prima della scadenza *(da decidere)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| NFR | NFR-03 | Controllo ruolo e classe lato backend (AC-11) |
| NFR | NFR-09 | Elenco compiti paginato (AC-01) ed errori uniformi (AC-11) |
| NFR | NFR-11 | Usabile da iPad, PC e smartphone (AC-10) |
| Assunzione | ASS-10 | La scuola usa Classroom per consegne e correzioni |
| Storia | DOC-04 | I compiti segnati dal docente |
| Storia | STU-01 | Stesso segno "nuovo" del materiale (AC-06) |

## Domande aperte per il team

1. Dopo un trasferimento lo studente deve vedere ancora i compiti della classe precedente? *(proposta: no, solo quelli della classe nuova, come il materiale in STU-01 AC-13)*
2. Il segno "nuovo" (AC-06) vi serve? Richiede di salvare l'ultimo accesso di ogni studente, come per materiale e voti.
