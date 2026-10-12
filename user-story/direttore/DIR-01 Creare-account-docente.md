# DIR-01 · Creare account docente

**Ruolo:** Direttore (ARC-001)

**Storia**

Come Direttore, voglio creare un account docente con le materie che può insegnare, per permettergli di accedere al sistema e operare sulle proprie classi.

---

## Acceptance criteria della traccia

> 💡 Riportare qui i 3 AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Creazione riuscita**
Dato che sono autenticato come Direttore, quando creo un account docente con nome, cognome, email e almeno una materia associata, allora il sistema invia al docente un'email con un link di attivazione, valido 48 ore. La password non viene mai generata dal sistema né mostrata al Direttore.

**AC-02 · Email già esistente**
Dato che inserisco un'email già registrata nel sistema (con qualsiasi ruolo), quando provo a salvare, allora il sistema rifiuta la creazione e mostra un errore chiaro.

**AC-03 · Stato "in attesa di attivazione"**
Dato che un docente non ha ancora attivato l'account, quando il Direttore consulta l'elenco docenti, allora lo stato dell'account è visibile come "in attesa di attivazione".

**AC-04 · Disattivazione**
Dato che il Direttore vuole disattivare (non eliminare) un account docente, quando conferma la disattivazione, allora il docente non può più accedere ma i suoi dati storici (verifiche create, voti assegnati) restano consultabili.

**AC-05 · Campi obbligatori e formato**
Dato che sono nel modulo di creazione docente, quando provo a salvare senza nome, cognome, email valida o almeno una materia, allora il sistema non crea l'account e indica quali campi sono mancanti o non validi.

**AC-06 · Materie da elenco predefinito**
Dato che sto associando le materie al docente, quando apro la selezione, allora posso scegliere solo fra le materie già presenti nel sistema (non posso scriverne di nuove a mano).

**AC-07 · Attivazione con il link**
Dato che il docente ha ricevuto l'email, quando apre il link entro 48 ore e sceglie la sua password, allora l'account passa ad "attivo" e il link non vale più. Da quel momento accede con email e password.

**AC-08 · Invio email fallito**
Dato che il servizio email non è raggiungibile, quando creo un account docente, allora l'account viene comunque salvato e il sistema riprova da solo l'invio (FR-ACC-01). Se non riesce, il Direttore vede la segnalazione "email non partita" e può reinviare il link dall'elenco docenti.

**AC-09 · Solo il Direttore può creare docenti**
Dato che sono autenticato come Docente o Studente, quando provo a creare un account docente (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

**AC-10 · Modifica dei dati del docente**
Dato che un account docente esiste, quando il Direttore modifica nome, cognome, email o materie e salva, allora i dati vengono aggiornati con le stesse regole della creazione (email unica, almeno una materia). Se toglie una materia che il docente insegna in qualche classe, il sistema lo avvisa e gli indica le classi coinvolte (DIR-04).

**AC-11 · Riattivazione**
Dato che un account docente è disattivato, quando il Direttore lo riattiva, allora il docente può di nuovo accedere con la sua password e ritrova i suoi dati storici.

**AC-12 · Password dimenticata**
Dato che il docente ha dimenticato la password, quando la richiede dalla pagina di accesso inserendo la propria email, allora riceve un link per sceglierne una nuova, valido 1 ora, senza passare dal Direttore. Se l'email non parte, la pagina gli chiede di riprovare più tardi.

**AC-13 · Link di attivazione scaduto**
Dato che il docente non ha aperto il link entro 48 ore, quando prova ad aprirlo, allora vede che il link è scaduto e che deve chiederne uno nuovo al Direttore. L'account resta "in attesa di attivazione" e il Direttore lo trova fra le segnalazioni (DIR-03). Quando il Direttore manda un link nuovo, quello vecchio smette di funzionare.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Nome | Sì | Testo, max 50 caratteri |
| Cognome | Sì | Testo, max 50 caratteri |
| Email | Sì | Formato valido, unica in tutto il sistema (tutti i ruoli) |
| Materie | Sì | Almeno una, scelte dall'elenco materie |

**Stati dell'account docente:** `in attesa di attivazione` → `attivo` → `disattivato` (riattivabile dal Direttore).

## Fuori perimetro di questa storia

- Assegnazione del docente alle classi → **DIR-04**
- Eliminazione definitiva dell'account (non prevista: si disattiva, per non perdere voti e verifiche)
- Gestione dell'elenco materie *(da decidere: chi lo popola? precaricato o gestito dal Direttore?)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| NFR | NFR-02 | HTTPS: password e link di attivazione non viaggiano in chiaro |
| Decisione | FR-ACC-01 | Invio del link di attivazione e fallimento dell'email (AC-01, AC-08, AC-13) |
| NFR | NFR-03 | Controllo ruolo lato backend (AC-09) |
| NFR | NFR-09 | Errori uniformi (AC-02, AC-05) ed elenco docenti paginato |
| Storia | DIR-04 | Il docente creato qui viene poi assegnato alle classi |
| Storia | DIR-03 | Il Direttore vede l'elenco docenti con il loro stato |

## Domande aperte per il team

1. Se un docente viene disattivato mentre è assegnato a delle classi, cosa succede alle classi? *(proposta: restano assegnate ma segnalate al Direttore come "senza docente attivo" finché non riassegna)*

