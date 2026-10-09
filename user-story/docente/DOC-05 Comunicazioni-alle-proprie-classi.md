# DOC-05 · Comunicazioni alle proprie classi

**Ruolo:** Docente (ARC-002)

**Storia**

Come Docente, voglio pubblicare comunicazioni alle mie classi e leggere quelle che ricevo dal Direttore, per avvisare gli studenti di cambi e novità e restare aggiornato su quello che succede nella scuola.

---

## Acceptance criteria della traccia

> 💡 Storia aggiunta dal team: la traccia non la prevede, quindi non ci sono AC della traccia da riportare.

## AC aggiunti dal team

**AC-01 · Pubblicazione alle mie classi**
Dato che sono autenticato come Docente, quando pubblico una comunicazione con titolo, testo e una o più delle mie classi, allora gli studenti e i docenti di quelle classi la vedono subito (STU-05).

**AC-02 · Solo le mie classi**
Dato che sto scrivendo una comunicazione, quando scelgo i destinatari, allora posso scegliere solo fra le classi in cui insegno (DIR-04). Non posso scrivere a tutta la scuola, a tutti i docenti o a tutti gli studenti (DIR-05 AC-12).

**AC-03 · Campi obbligatori**
Dato che sono nel modulo della comunicazione, quando provo a pubblicare senza titolo, senza testo o senza classe, allora il sistema non la pubblica e indica cosa manca.

**AC-04 · Link**
Dato che voglio rimandare a una pagina o a un compito su Classroom, quando incollo un link, allora gli studenti lo aprono in una nuova scheda. Le schede da studiare vanno nel materiale didattico (DOC-01).

**AC-05 · Modifica ed eliminazione**
Dato che ho pubblicato una comunicazione, quando la modifico o la elimino, allora valgono le stesse regole del Direttore: la comunicazione modificata è segnata "modificata", l'eliminazione chiede conferma (DIR-05 AC-07, AC-08).

**AC-06 · Comunicazioni che ricevo**
Dato che sono autenticato come Docente, quando apro la sezione Comunicazioni, allora vedo, dalla più recente, quelle del Direttore a tutta la scuola, ai docenti o alle mie classi, e quelle degli altri docenti alle mie classi. Le comunicazioni in evidenza sono in cima e quelle non ancora lette sono segnate "nuova".

**AC-07 · Le mie comunicazioni**
Dato che apro la sezione Comunicazioni, quando scelgo "Inviate da me", allora vedo le comunicazioni che ho pubblicato, con classi e data, in un elenco paginato.

**AC-08 · Nessuna risposta**
Dato che pubblico una comunicazione, quando gli studenti la leggono, allora non possono rispondere (DIR-05 AC-11).

**AC-09 · Solo i docenti della classe**
Dato che sono autenticato come Studente, oppure come Docente di un'altra classe, quando provo a pubblicare una comunicazione a una classe (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Titolo | Sì | Testo, max 100 caratteri |
| Testo | Sì | Testo, max 3000 caratteri |
| Classi | Sì | Almeno una, fra quelle in cui il docente insegna |
| Link | No | URL valido http/https |

- I docenti non hanno allegati né il segno "in evidenza": sono del Direttore (DIR-05).
- Mittente e data vengono registrati in automatico.

## Fuori perimetro di questa storia

- Comunicazioni a tutta la scuola o ai docenti → **DIR-05**
- Lettura da parte degli studenti → **STU-05**
- Comunicazione a un singolo studente (sarebbe un messaggio privato, quindi chat: fuori perimetro)
- Email e notifiche *(da decidere, come in DIR-05)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| NFR | NFR-03 | Controllo ruolo e classe lato backend (AC-09) |
| NFR | NFR-09 | Elenchi paginati (AC-06, AC-07) ed errori uniformi (AC-03) |
| Storia | DIR-04 | Le classi in cui il docente insegna (AC-02) |
| Storia | DIR-05 | Stesse regole delle comunicazioni del Direttore |
| Storia | STU-05 | Gli studenti leggono le comunicazioni |

## Domande aperte per il team

1. Un docente vede anche le comunicazioni degli altri docenti alle sue classi (AC-06)? *(proposta: sì, così sa cosa è già stato detto alla classe)*
2. Servono gli allegati anche per i docenti, o bastano link e materiale didattico?
