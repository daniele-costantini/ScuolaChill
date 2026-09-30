# DIR-04 · Creare classi e comporle

**Ruolo:** Direttore (ARC-001)

**Storia**

Come Direttore, voglio creare le classi e comporle assegnando studenti, materie e docenti, per permettere a ognuno di vedere e lavorare solo sulla propria classe.

---

## Acceptance criteria della traccia

> 💡 Riportare qui gli AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Creazione classe**
Dato che sono autenticato come Direttore, quando creo una classe indicando il nome (es. "3A") e l'anno scolastico (es. "2026/2027"), allora la classe compare nell'elenco classi, inizialmente vuota.

**AC-02 · Nome classe unico**
Dato che esiste già una classe "3A" per l'anno 2026/2027, quando provo a crearne un'altra con lo stesso nome nello stesso anno, allora il sistema rifiuta la creazione e mostra un errore chiaro.

**AC-03 · Aggiunta studenti**
Dato che ho creato una classe, quando seleziono uno o più studenti dall'elenco "senza classe", allora vengono iscritti alla classe e spariscono dall'elenco degli studenti da assegnare.

**AC-04 · Uno studente, una classe**
Dato che uno studente è già iscritto a una classe, quando provo ad aggiungerlo a un'altra, allora il sistema non lo iscrive a due classi e mi propone invece il trasferimento (AC-08).

**AC-05 · Materie e docenti della classe**
Dato che sto componendo una classe, quando aggiungo una materia dall'elenco materie e le assegno un docente, allora quel docente vede la classe fra le proprie e può operare su di essa solo per quella materia.

**AC-06 · Docente abilitato alla materia**
Dato che sto assegnando un docente a una materia della classe, quando apro la scelta del docente, allora vedo solo i docenti attivi che hanno quella materia fra quelle che possono insegnare (DIR-01).

**AC-07 · Un docente per materia**
Dato che una materia della classe ha già un docente, quando ne assegno un altro, allora il nuovo docente sostituisce il precedente, e le verifiche e i voti già inseriti restano associati a chi li ha creati.

**AC-08 · Trasferimento di uno studente** *(proposta per la decisione aperta, da confermare con il team)*
Dato che uno studente è iscritto alla classe A, quando lo trasferisco alla classe B e confermo, allora lo studente vede da quel momento materiale e verifiche della classe B, mentre i voti già ricevuti restano nel suo storico con l'indicazione della classe A in cui li ha presi.

**AC-09 · Rimozione di uno studente**
Dato che uno studente è iscritto a una classe, quando lo rimuovo dalla classe, allora torna fra gli studenti "senza classe" e i suoi voti restano nel suo storico.

**AC-10 · Eliminazione classe**
Dato che voglio eliminare una classe, quando la classe non ha studenti, verifiche né voti, allora posso eliminarla; altrimenti il sistema me lo impedisce e spiega il motivo.

**AC-11 · Riepilogo della classe**
Dato che apro una classe, quando la consulto, allora vedo l'elenco degli studenti iscritti, le materie con il rispettivo docente e le materie ancora senza docente evidenziate.

**AC-12 · Solo il Direttore compone le classi**
Dato che sono autenticato come Docente o Studente, quando provo a creare o modificare una classe (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Nome | Sì | Testo breve (es. "3A"), unico nello stesso anno scolastico |
| Anno scolastico | Sì | Formato "AAAA/AAAA" |
| Studenti | No | Solo studenti attivi o in attesa di attivazione, senza classe |
| Materie | No | Scelte dall'elenco materie, ognuna al massimo una volta per classe |
| Docente per materia | No | Uno solo, attivo e abilitato a quella materia |

- Uno studente appartiene al massimo a una classe alla volta (come in DIR-02).
- Un docente può insegnare in più classi e più materie (ARC-002).
- Una materia senza docente è ammessa, ma compare fra le segnalazioni della vista d'insieme (DIR-03).
- Con 484 studenti e 21 classi, una classe ha in media circa 23 studenti.

## Fuori perimetro di questa storia

- Creazione degli account di docenti e studenti → **DIR-01**, **DIR-02**
- Gestione dell'elenco materie *(da decidere: chi lo popola? precaricato o gestito dal Direttore?)*
- Passaggio automatico delle classi all'anno successivo *(da decidere se va in "Cosa non è incluso" del PRD)*
- Orario delle lezioni (fuori perimetro del PRD)

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Decisione aperta | Trasferimento fra classi | Proposta in AC-08; una volta confermata va scritta come FR nel PRD |
| NFR | NFR-03 | Controllo ruolo lato backend (AC-12) |
| NFR | NFR-09 | Errori uniformi (AC-02, AC-10) ed elenchi paginati |
| Storia | DIR-01 | Il docente e le materie che può insegnare (AC-06) |
| Storia | DIR-02 | Gli studenti "senza classe" da assegnare (AC-03) |
| Storia | DIR-03 | Le segnalazioni (studenti senza classe, materie senza docente) portano qui |
| Storia | DOC-01, DOC-02, DOC-03 | Il docente opera solo sulle classi e materie assegnate qui |
| Storia | STU-01, STU-02, STU-03 | Lo studente vede materiale, verifiche e voti della propria classe |

## Domande aperte per il team

1. Confermate la proposta sul trasferimento (AC-08)? In alternativa: trasferimento non consentito durante l'anno, oppure i voti si spostano nella nuova classe.
2. Cosa succede a una materia se il suo docente viene disattivato? *(proposta: la materia resta senza docente e compare fra le segnalazioni di DIR-03)*
3. Le classi sono legate a un anno scolastico (come in AC-01) o esiste un solo anno?
4. Una materia può avere due docenti nella stessa classe (es. compresenza, sostegno)? *(proposta: no, uno solo, come in AC-07)*
