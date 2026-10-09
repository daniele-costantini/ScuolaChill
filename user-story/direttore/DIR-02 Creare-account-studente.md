# DIR-02 · Creare account studente

**Ruolo:** Direttore (ARC-001)

**Storia**

Come Direttore, voglio creare un account studente, per permettergli di accedere al sistema, consultare il materiale, svolgere le verifiche e vedere i propri voti.

---

## Acceptance criteria della traccia

> 💡 Riportare qui gli AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Creazione riuscita**
Dato che sono autenticato come Direttore, quando creo un account studente con nome, cognome ed email, allora il sistema genera le credenziali e le invia via email allo studente.

**AC-02 · Email già esistente**
Dato che inserisco un'email già registrata nel sistema (con qualsiasi ruolo), quando provo a salvare, allora il sistema rifiuta la creazione e mostra un errore chiaro.

**AC-03 · Campi obbligatori e formato**
Dato che sono nel modulo di creazione studente, quando provo a salvare senza nome, cognome o un'email valida, allora il sistema non crea l'account e indica quali campi sono mancanti o non validi.

**AC-04 · Classe facoltativa alla creazione**
Dato che sto creando uno studente, quando scelgo una classe dall'elenco delle classi esistenti, allora lo studente risulta iscritto a quella classe; se non la scelgo, l'account viene creato "senza classe" e compare fra gli studenti da assegnare in DIR-04.

**AC-05 · Stato "in attesa di attivazione"**
Dato che uno studente non ha ancora effettuato il primo accesso, quando il Direttore consulta l'elenco studenti, allora lo stato dell'account è visibile come "in attesa di attivazione".

**AC-06 · Cambio password al primo accesso**
Dato che lo studente accede per la prima volta con le credenziali ricevute via email, quando effettua il login, allora il sistema lo obbliga a impostare una nuova password prima di usare l'applicazione, e lo stato dell'account passa ad "attivo".

**AC-07 · Invio email fallito**
Dato che il servizio email non è raggiungibile, quando creo un account studente, allora l'account viene comunque salvato, il Direttore viene avvisato che l'email non è partita e può richiedere un nuovo invio delle credenziali dall'elenco studenti.

**AC-08 · Disattivazione**
Dato che il Direttore vuole disattivare (non eliminare) un account studente, quando conferma la disattivazione, allora lo studente non può più accedere ma i suoi voti e le verifiche svolte restano consultabili dal Direttore e dai docenti.

**AC-09 · Solo il Direttore può creare studenti**
Dato che sono autenticato come Docente o Studente, quando provo a creare un account studente (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

**AC-10 · Creazione da file** *(proposta, da confermare con il team)*
Dato che devo inserire molti studenti (la scuola ne ha 500), quando carico un file CSV con nome, cognome, email ed eventuale classe, allora il sistema crea gli account validi, invia le credenziali e mi mostra un riepilogo delle righe scartate con il motivo (email duplicata, campo mancante, classe inesistente).

**AC-11 · Modifica dei dati dello studente**
Dato che un account studente esiste, quando il Direttore modifica nome, cognome o email e salva, allora i dati vengono aggiornati con le stesse regole della creazione (email unica, campi obbligatori). Il cambio di classe non si fa qui ma con il trasferimento (DIR-04).

**AC-12 · Riattivazione**
Dato che un account studente è disattivato, quando il Direttore lo riattiva, allora lo studente può di nuovo accedere e ritrova i suoi voti.

**AC-13 · Password dimenticata** *(proposta, da confermare con il team)*
Dato che lo studente ha dimenticato la password, quando la richiede dalla pagina di accesso inserendo la propria email, allora riceve un link per impostarne una nuova, senza passare dal Direttore. Se l'email non parte, il Direttore può reinviare le credenziali dall'elenco studenti (FR-EXT-01).

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Nome | Sì | Testo, max 50 caratteri |
| Cognome | Sì | Testo, max 50 caratteri |
| Email | Sì | Formato valido, unica in tutto il sistema (tutti i ruoli) |
| Classe | No | Una sola, scelta fra le classi esistenti |

**Stati dell'account studente:** `in attesa di attivazione` → `attivo` → `disattivato` (riattivabile dal Direttore). Sono gli stessi stati del docente (DIR-01).

**Uno studente appartiene al massimo a una classe alla volta.**

## Fuori perimetro di questa storia

- Composizione delle classi e spostamento di uno studente fra classi → **DIR-04** (decisione aperta sul trasferimento)
- Eliminazione definitiva dell'account (non prevista: si disattiva, per non perdere i voti)
- Account dei genitori (le comunicazioni con le famiglie sono fuori perimetro del PRD)

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Decisione aperta | FR-EXT-01 · Fallimento del servizio email | Coperta da AC-07 |
| Decisione aperta | Trasferimento fra classi (DIR-04) | AC-04 assegna solo la classe iniziale |
| NFR | NFR-02 | HTTPS: le credenziali non viaggiano in chiaro |
| NFR | NFR-03 | Controllo ruolo lato backend (AC-09) |
| NFR | NFR-09 | Errori uniformi (AC-02, AC-03) ed elenco studenti paginato |
| Storia | DIR-01 | Stessa gestione di credenziali, stati e disattivazione |
| Storia | DIR-04 | Lo studente creato qui viene iscritto o spostato di classe |
| Storia | DIR-03 | Il Direttore vede l'elenco studenti con il loro stato |

## Domande aperte per il team

1. La classe va scelta obbligatoriamente alla creazione, o si può lasciare vuota come in AC-04? *(proposta: facoltativa, perché a inizio anno le classi potrebbero non esistere ancora)*
2. Vogliamo la creazione da CSV (AC-10)? Con 500 studenti, inserirli uno alla volta è poco realistico per il Direttore, ma aggiunge lavoro.
3. Gli studenti sono minorenni: l'email è la loro personale, una istituzionale della scuola o quella di un genitore?
4. Uno studente disattivato resta iscritto alla sua classe (e compare nei registri dei docenti) o ne viene tolto?
5. Confermate il recupero password in autonomia (AC-13)? Deve essere la stessa scelta fatta per i docenti (DIR-01, AC-12).
