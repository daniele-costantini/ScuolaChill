# DOC-04 · Assegnare i compiti per casa

**Ruolo:** Docente (ARC-002)

**Storia**

Come Docente, voglio segnare sul registro i compiti per casa delle mie classi, con la scadenza e il link al compito su Classroom, perché gli studenti sappiano cosa devono fare, entro quando e dove consegnarlo.

---

## Acceptance criteria della traccia

> 💡 Storia aggiunta dal team: la traccia non la prevede, quindi non ci sono AC della traccia da riportare.

## AC aggiunti dal team

**AC-01 · Compito segnato**
Dato che sono autenticato come Docente, quando segno un compito indicando titolo, descrizione, classe, materia e scadenza, allora il compito viene salvato e compare subito fra i compiti di quella classe e materia, visibile agli studenti (STU-04).

**AC-02 · Solo le mie classi e materie**
Dato che sto segnando un compito, quando scelgo classe e materia, allora posso scegliere solo fra le coppie classe/materia che il Direttore mi ha assegnato (DIR-04).

**AC-03 · Campi obbligatori**
Dato che sono nel modulo del compito, quando provo a salvare senza titolo, senza classe e materia o senza scadenza, oppure con una scadenza già passata, allora il sistema non salva il compito e indica cosa manca o cosa è sbagliato.

**AC-04 · Link al compito su Classroom**
Dato che il compito si consegna su Classroom, quando incollo il link, allora il compito lo mostra e lo studente lo apre in una nuova scheda. Il link è facoltativo: un compito sul libro da correggere in classe non ne ha bisogno.

**AC-05 · Nessuna consegna su ScuolaChill**
Dato che segno un compito, quando lo salvo, allora ScuolaChill non chiede e non accetta consegne né file: consegna e correzione avvengono su Classroom o in classe.

**AC-06 · Stesso compito in più classi**
Dato che insegno la stessa materia in più classi, quando segno un compito, allora posso selezionare più classi insieme e il compito compare in ognuna, senza doverlo scrivere più volte.

**AC-07 · Modifica**
Dato che ho segnato un compito, quando ne modifico descrizione, link o scadenza e salvo, allora gli studenti vedono subito la versione aggiornata, segnata come "modificato". Posso spostare la scadenza anche dopo che è passata.

**AC-08 · Eliminazione**
Dato che ho segnato un compito, quando lo elimino e confermo, allora non è più visibile agli studenti. Il sistema mi chiede conferma prima di eliminarlo.

**AC-09 · Elenco dei miei compiti**
Dato che apro una mia classe e materia, quando consulto i compiti, allora li vedo ordinati per scadenza, dal più vicino, con titolo, scadenza e link, in un elenco paginato.

**AC-10 · Voto del compito** *(proposta, da confermare)*
Dato che ho corretto un compito su Classroom e voglio valutarlo, quando inserisco il voto su ScuolaChill come prova svolta fuori da ScuolaChill (DOC-03 AC-05), allora scelgo il tipo di prova "compito" e il voto segue le regole di DOC-03.

**AC-11 · Compiti di chi non insegna più la materia**
Dato che il Direttore ha assegnato la materia della classe a un altro docente (DIR-04), quando uno studente apre i compiti, allora continua a vedere quelli che ho segnato; il nuovo docente può modificarli o eliminarli (come DOC-01 AC-12).

**AC-12 · Solo il docente della classe e materia**
Dato che sono autenticato come Studente, quando provo a segnare, modificare o eliminare un compito (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione. Lo stesso vale per un Docente che prova a farlo su una classe o materia non sua.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Titolo | Sì | Testo, max 100 caratteri |
| Descrizione | No | Testo, max 1000 caratteri (es. "Esercizi da 4 a 10 di pagina 132") |
| Link | No | URL valido http/https, di solito il compito su Classroom |
| Classi | Sì | Almeno una, fra quelle in cui il docente insegna la materia scelta |
| Materia | Sì | Una sola, fra quelle assegnate al docente |
| Scadenza | Sì | Data (e ora, se serve), non nel passato |

- Il compito appartiene alla coppia classe/materia, non al docente, come il materiale (DOC-01 AC-12).
- ScuolaChill non salva file per i compiti: solo testo e link. Non c'è spazio per i file da pagare.
- Data di creazione e autore vengono registrati in automatico.
- Ordine di grandezza: circa 10 compiti a settimana per classe, quindi 23 classi × 10 × 33 settimane ≈ 7.600 compiti l'anno, pochi KB ciascuno.

## Fuori perimetro di questa storia

- Consultazione dei compiti da parte degli studenti → **STU-04**
- Consegna e correzione dei compiti: avvengono su Classroom o in classe
- Collegamento con Classroom (ScuolaChill mostra solo il link, non legge né scrive nulla su Classroom)
- Allegati caricati su ScuolaChill: le schede si mettono nel materiale didattico (DOC-01) o su Classroom
- Promemoria o notifiche prima della scadenza *(da decidere)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| NFR | NFR-03 | Controllo ruolo e classe/materia lato backend (AC-12) |
| NFR | NFR-09 | Errori uniformi (AC-03) ed elenco compiti paginato (AC-09) |
| Assunzione | ASS-10 | La scuola usa Classroom per consegne e correzioni |
| Storia | DIR-04 | Le classi e materie su cui il docente può segnare compiti (AC-02) |
| Storia | DOC-03 | Voto del compito, inserito come prova fuori da ScuolaChill (AC-10) |
| Storia | STU-04 | Lo studente vede i compiti segnati qui |

## Domande aperte per il team

1. Il voto del compito va inserito su ScuolaChill (AC-10), o resta solo su Classroom?
2. Serve l'ora della scadenza, o basta il giorno ("per giovedì")?
3. Il Direttore vede i compiti nella vista d'insieme (DIR-03), per esempio quanti compiti ha ogni classe a settimana?
