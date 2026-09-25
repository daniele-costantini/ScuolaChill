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
Dato che sono autenticato come Direttore, quando creo un account docente con nome, cognome, email e almeno una materia associata, allora il sistema genera le credenziali e le invia via email al docente.

**AC-02 · Email già esistente**
Dato che inserisco un'email già registrata nel sistema (con qualsiasi ruolo), quando provo a salvare, allora il sistema rifiuta la creazione e mostra un errore chiaro.

**AC-03 · Stato "in attesa di attivazione"**
Dato che un docente non ha ancora effettuato il primo accesso, quando il Direttore consulta l'elenco docenti, allora lo stato dell'account è visibile come "in attesa di attivazione".

**AC-04 · Disattivazione**
Dato che il Direttore vuole disattivare (non eliminare) un account docente, quando conferma la disattivazione, allora il docente non può più accedere ma i suoi dati storici (verifiche create, voti assegnati) restano consultabili.

**AC-05 · Campi obbligatori e formato**
Dato che sono nel modulo di creazione docente, quando provo a salvare senza nome, cognome, email valida o almeno una materia, allora il sistema non crea l'account e indica quali campi sono mancanti o non validi.

**AC-06 · Materie da elenco predefinito**
Dato che sto associando le materie al docente, quando apro la selezione, allora posso scegliere solo fra le materie già presenti nel sistema (non posso scriverne di nuove a mano).

**AC-07 · Cambio password al primo accesso**
Dato che il docente accede per la prima volta con le credenziali ricevute via email, quando effettua il login, allora il sistema lo obbliga a impostare una nuova password prima di usare l'applicazione, e lo stato dell'account passa ad "attivo".

**AC-08 · Invio email fallito**
Dato che il servizio email non è raggiungibile, quando creo un account docente, allora l'account viene comunque salvato, il Direttore viene avvisato che l'email non è partita e può richiedere un nuovo invio delle credenziali dall'elenco docenti.

**AC-09 · Solo il Direttore può creare docenti**
Dato che sono autenticato come Docente o Studente, quando provo a creare un account docente (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

**AC-10 · Modifica dei dati del docente**
Dato che un account docente esiste, quando il Direttore modifica nome, cognome, email o materie e salva, allora i dati vengono aggiornati con le stesse regole della creazione (email unica, almeno una materia). Se toglie una materia che il docente insegna in qualche classe, il sistema lo avvisa e gli indica le classi coinvolte (DIR-04).

**AC-11 · Riattivazione**
Dato che un account docente è disattivato, quando il Direttore lo riattiva, allora il docente può di nuovo accedere con le sue credenziali e ritrova i suoi dati storici.

**AC-12 · Password dimenticata** *(proposta, da confermare con il team)*
Dato che il docente ha dimenticato la password, quando la richiede dalla pagina di accesso inserendo la propria email, allora riceve un link per impostarne una nuova, senza passare dal Direttore. Se l'email non parte, il Direttore può reinviare le credenziali dall'elenco docenti (FR-EXT-01).

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
| Decisione aperta | FR-EXT-01 · Fallimento del servizio email | Coperta da AC-08 |
| NFR | NFR-02 | HTTPS: le credenziali non viaggiano in chiaro |
| NFR | NFR-03 | Controllo ruolo lato backend (AC-09) |
| NFR | NFR-09 | Errori uniformi (AC-02, AC-05) ed elenco docenti paginato |
| Storia | DIR-04 | Il docente creato qui viene poi assegnato alle classi |
| Storia | DIR-03 | Il Direttore vede l'elenco docenti con il loro stato |

## Domande aperte per il team

1. Se un docente viene disattivato mentre è assegnato a delle classi, cosa succede alle classi? *(proposta: restano assegnate ma segnalate al Direttore come "senza docente attivo" finché non riassegna)*
2. Le credenziali inviate hanno una scadenza? *(proposta: password temporanea valida 7 giorni, poi va rigenerata)*
3. Confermate il recupero password in autonomia (AC-12)? In alternativa se ne occupa il Direttore, ma con 502 utenti diventa un carico pesante.
