# DOC-06 · Assegnare note disciplinari

**Ruolo:** Docente (ARC-002)

**Storia**

Come Docente, voglio segnare sul registro una nota disciplinare a uno studente o a tutta la classe, perché resti traccia del comportamento e lo studente e il Direttore ne siano informati.

---

## Acceptance criteria della traccia

> 💡 Storia aggiunta dal team: la traccia non la prevede, quindi non ci sono AC della traccia da riportare.

## AC aggiunti dal team

**AC-01 · Nota a uno studente**
Dato che sono autenticato come Docente, quando segno una nota scegliendo lo studente, la data e il motivo, allora la nota è salvata e la vedono subito lo studente (STU-05) e il Direttore.

**AC-02 · Solo gli studenti delle mie classi**
Dato che sto segnando una nota, quando scelgo lo studente, allora posso scegliere solo fra gli studenti delle classi in cui insegno (DIR-04).

**AC-03 · Campi obbligatori**
Dato che sono nel modulo della nota, quando provo a salvare senza studente, senza motivo o con una data futura, allora il sistema non la salva e indica cosa manca o cosa è sbagliato.

**AC-04 · Nota alla classe**
Dato che tutta la classe si è comportata male, quando segno una nota alla classe, allora la nota è salvata una volta sola e la vede ogni studente della classe, fra le sue note.

**AC-05 · Chi vede la nota**
Dato che ho segnato una nota a uno studente, quando qualcuno prova a vederla, allora la vedono solo lo studente interessato, io, gli altri docenti della sua classe e il Direttore. Gli altri studenti non la vedono mai, neanche chiamando direttamente l'API.

**AC-06 · I colleghi vedono ma non modificano**
Dato che sono un docente della classe ma non ho scritto io la nota, quando la apro, allora la vedo in sola lettura: non posso modificarla né annullarla, neanche chiamando direttamente l'API. Può farlo solo chi l'ha scritta (AC-07, AC-08) o il Direttore (AC-09).

**AC-07 · Modifica con storico**
Dato che ho segnato una nota, quando ne correggo il testo o la data, allora lo studente vede la versione nuova, segnata come "modificata", e il sistema tiene traccia di chi ha cambiato cosa e quando (come per i voti, DOC-03 AC-11).

**AC-08 · Annullamento** *(proposta, da confermare)*
Dato che ho segnato una nota per errore, quando la annullo indicando il motivo, allora la nota non viene cancellata: risulta "annullata", lo studente la vede come tale e il motivo resta nello storico.

**AC-09 · Il Direttore vede e annulla**
Dato che sono autenticato come Direttore, quando consulto le note, allora vedo quelle di tutta la scuola, filtrabili per classe e studente, e posso annullarne una con un motivo (AC-08). Non posso scriverne di nuove.

**AC-10 · Note della classe**
Dato che apro una mia classe, quando consulto le note, allora vedo quelle di tutti i docenti agli studenti della classe, dalla più recente, con studente, data, docente e motivo, in un elenco paginato.

**AC-11 · Nessun effetto su voti e medie**
Dato che uno studente ha una o più note, quando si calcolano voti e medie (DOC-03, STU-03, DIR-03), allora le note non contano: non esiste un voto di condotta calcolato da ScuolaChill.

**AC-12 · Solo i docenti scrivono note**
Dato che sono autenticato come Studente, quando provo a segnare, modificare o annullare una nota (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione. Lo stesso vale per un Docente che prova a farlo su uno studente di una classe non sua.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Destinatario | Sì | Uno studente, oppure tutta la classe |
| Classe | Sì | Fra quelle in cui il docente insegna |
| Data | Sì | Oggi o nel passato, non nel futuro |
| Motivo | Sì | Testo, max 1000 caratteri |

**Stati della nota:** `attiva` → `annullata` (con motivo). Ogni modifica resta nello storico.

- Docente autore, data e ora di inserimento vengono registrati in automatico.
- Le note sono dati personali delicati di minori (VIN-07): chi le vede è deciso in AC-05, e nessuna nota si cancella senza traccia.
- Ordine di grandezza: poche note a settimana in tutta la scuola, un'operazione rara e leggera.

## Fuori perimetro di questa storia

- Lettura da parte dello studente → **STU-05**
- Voto di condotta e scrutinio
- Provvedimenti disciplinari (sospensioni, convocazioni)
- Avviso alle famiglie (non ci sono account per i genitori)
- Risposta o giustificazione dello studente alla nota

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Vincolo | VIN-07 | GDPR: le note sono dati delicati di minori (AC-05) |
| NFR | NFR-03 | Controllo ruolo, classe e studente lato backend (AC-05, AC-12) |
| NFR | NFR-09 | Elenco paginato (AC-10) ed errori uniformi (AC-03) |
| Storia | DIR-04 | Gli studenti delle classi in cui il docente insegna (AC-02) |
| Storia | DOC-03 | Stesso storico delle modifiche dei voti (AC-07) |
| Storia | STU-05 | Lo studente legge le sue note |

## Domande aperte per il team

1. Annullare invece di eliminare (AC-08) vi va bene?
2. Per quanto tempo restano le note? *(proposta: per tutto l'anno scolastico, poi visibili solo al Direttore)*
3. La vista d'insieme del Direttore (DIR-03) deve mostrare quante note ha ogni classe?
