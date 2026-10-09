# DIR-05 · Pubblicare comunicazioni

**Ruolo:** Direttore (ARC-001)

**Storia**

Come Direttore, voglio pubblicare comunicazioni a tutta la scuola, ai soli docenti, ai soli studenti o a una o più classi, per avvisare tutti in un posto solo, senza fogli in bacheca.

---

## Acceptance criteria della traccia

> 💡 Storia aggiunta dal team: la traccia non la prevede, quindi non ci sono AC della traccia da riportare.

## AC aggiunti dal team

**AC-01 · Pubblicazione riuscita**
Dato che sono autenticato come Direttore, quando pubblico una comunicazione con titolo, testo e destinatari, allora la comunicazione è salvata e i destinatari la vedono subito nella sezione Comunicazioni (DOC-05, STU-05).

**AC-02 · Destinatari**
Dato che sto scrivendo una comunicazione, quando scelgo i destinatari, allora posso scegliere fra tutta la scuola, tutti i docenti, tutti gli studenti, oppure una o più classi (gli studenti e i docenti di quelle classi).

**AC-03 · Campi obbligatori**
Dato che sono nel modulo della comunicazione, quando provo a pubblicare senza titolo, senza testo o senza destinatari, allora il sistema non la pubblica e indica cosa manca.

**AC-04 · Allegato o link** *(proposta, da confermare)*
Dato che la comunicazione ha una circolare o un modulo, quando allego un PDF (max 5 MB) o incollo un link, allora i destinatari lo aprono dal dettaglio della comunicazione.

**AC-05 · Comunicazione in evidenza**
Dato che una comunicazione è importante, quando la segno "in evidenza", allora resta in cima all'elenco dei destinatari finché non tolgo il segno o finché non scade (AC-06).

**AC-06 · Scadenza** *(proposta, da confermare)*
Dato che una comunicazione vale fino a una certa data (per esempio "Uscita anticipata venerdì"), quando indico la scadenza, allora dopo quella data la comunicazione passa fra quelle vecchie, sempre consultabile.

**AC-07 · Modifica**
Dato che ho pubblicato una comunicazione, quando la modifico e salvo, allora i destinatari vedono la versione nuova, segnata come "modificata" con la data della modifica.

**AC-08 · Eliminazione**
Dato che ho pubblicato una comunicazione, quando la elimino e confermo, allora non è più visibile ai destinatari. Il sistema mi chiede conferma prima.

**AC-09 · Letture** *(proposta, da confermare)*
Dato che ho pubblicato una comunicazione, quando la apro, allora vedo quanti destinatari l'hanno letta sul totale, così capisco se l'avviso è arrivato.

**AC-10 · Elenco delle comunicazioni**
Dato che apro la sezione Comunicazioni, quando la consulto, allora vedo tutte le comunicazioni della scuola, anche quelle dei docenti alle loro classi, dalla più recente, con mittente, destinatari e data, in un elenco paginato e filtrabile per classe.

**AC-11 · Nessuna risposta**
Dato che pubblico una comunicazione, quando i destinatari la leggono, allora non possono rispondere: le comunicazioni vanno in una sola direzione (la chat è fuori dal perimetro).

**AC-12 · Solo il Direttore scrive a tutta la scuola**
Dato che sono autenticato come Docente o Studente, quando provo a pubblicare una comunicazione a tutta la scuola, a tutti i docenti o a tutti gli studenti (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Titolo | Sì | Testo, max 100 caratteri |
| Testo | Sì | Testo, max 3000 caratteri |
| Destinatari | Sì | Tutta la scuola, tutti i docenti, tutti gli studenti, oppure una o più classi |
| Allegato | No | Un PDF, max 5 MB *(proposta)*, oppure un link http/https |
| In evidenza | No | Sì o no |
| Scadenza | No | Data, non nel passato *(proposta)* |

- Mittente e data di pubblicazione vengono registrati in automatico.
- Le comunicazioni restano nella sezione: non partono email né notifiche, quindi niente costi né dipendenze in più.
- Ordine di grandezza: qualche comunicazione a settimana dal Direttore; ogni comunicazione a tutta la scuola arriva a circa 520 persone.

## Fuori perimetro di questa storia

- Comunicazioni dei docenti alle proprie classi → **DOC-05**
- Lettura da parte degli studenti → **STU-05**
- Invio per email o notifiche sul dispositivo *(da decidere)*
- Risposte e chat
- Comunicazioni alle famiglie (non ci sono account per i genitori)
- Pubblicazione programmata a una data futura *(da decidere)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| NFR | NFR-03 | Controllo ruolo lato backend (AC-12) |
| NFR | NFR-09 | Elenco paginato (AC-10) ed errori uniformi (AC-03) |
| Dipendenza | DIP-04 | Spazio per i file, se si confermano gli allegati PDF (AC-04) |
| Storia | DIR-04 | Le classi a cui si può scrivere (AC-02) |
| Storia | DOC-05 | I docenti leggono le comunicazioni del Direttore e scrivono alle loro classi |
| Storia | STU-05 | Gli studenti leggono le comunicazioni |

## Domande aperte per il team

1. Servono gli allegati PDF (AC-04), o basta un link? Gli allegati usano lo spazio per i file.
2. Vi serve il conteggio delle letture (AC-09)? Richiede di salvare chi ha aperto ogni comunicazione.
3. Il Direttore può modificare o eliminare le comunicazioni dei docenti?
