# DOC-02 · Creare le proprie verifiche

**Ruolo:** Docente (ARC-002)

**Storia**

Come Docente, voglio creare verifiche online per le mie classi e materie, per farle svolgere agli studenti su ScuolaChill e avere le risposte già raccolte in un posto solo.

---

## Acceptance criteria della traccia

> 💡 Riportare qui gli AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Creazione in bozza**
Dato che sono autenticato come Docente, quando creo una verifica indicando titolo, classe e materia, allora la verifica viene salvata come "bozza", visibile solo a me, e posso aggiungere le domande con calma.

**AC-02 · Solo le mie classi e materie**
Dato che sto creando una verifica, quando scelgo classe e materia, allora posso scegliere solo fra le coppie classe/materia che il Direttore mi ha assegnato (DIR-04).

**AC-03 · Tipi di domanda**
Dato che sto componendo la verifica, quando aggiungo una domanda, allora posso scegliere fra risposta multipla (una sola corretta), vero/falso e risposta aperta, e assegnare a ogni domanda un punteggio.

**AC-04 · Domande chiuse con risposta corretta**
Dato che aggiungo una domanda a risposta multipla o vero/falso, quando la salvo, allora il sistema mi obbliga a indicare la risposta corretta e, per la risposta multipla, almeno due opzioni.

**AC-05 · Ordine delle domande**
Dato che la verifica ha più domande, quando ne cambio l'ordine o ne elimino una, allora la verifica si aggiorna e il punteggio totale viene ricalcolato.

**AC-06 · Finestra di svolgimento**
Dato che la verifica è pronta, quando imposto data e ora di apertura, data e ora di chiusura e la durata massima per ogni studente, allora il sistema accetta solo una chiusura successiva all'apertura e una durata che ci stia dentro.

**AC-07 · Pubblicazione**
Dato che la verifica ha almeno una domanda e una finestra valida, quando la pubblico, allora passa a "programmata" e gli studenti della classe la vedono in elenco, ma possono aprirla solo dall'ora di apertura (STU-02). Non posso pubblicare una verifica senza domande.

**AC-08 · Anteprima**
Dato che sto preparando la verifica, quando apro l'anteprima, allora la vedo come la vedrà lo studente, senza le risposte corrette.

**AC-09 · Modifica prima dell'apertura**
Dato che la verifica è in bozza o programmata e l'ora di apertura non è ancora arrivata, quando modifico domande, punteggi o finestra, allora le modifiche vengono salvate senza limiti.

**AC-10 · Modifica dopo l'apertura** *(proposta per la decisione aperta, da confermare con il team)*
Dato che almeno uno studente ha iniziato la verifica, quando provo a modificarla, allora non posso più cambiare domande, risposte corrette e punteggi. Posso solo:
- spostare più avanti l'ora di chiusura;
- annullare una domanda sbagliata: non conta per nessuno e i punteggi di tutti vengono ricalcolati;
- annullare l'intera verifica, se nessun voto è ancora stato assegnato (DOC-03).

**AC-11 · Duplicazione**
Dato che ho già creato una verifica, quando la duplico, allora ottengo una nuova bozza con le stesse domande, da assegnare a un'altra mia classe o da riusare l'anno dopo.

**AC-12 · Eliminazione**
Dato che la verifica è in bozza o programmata e nessuno studente l'ha iniziata, quando la elimino e confermo, allora sparisce anche dall'elenco degli studenti. Una verifica già svolta non si elimina (vedi AC-10).

**AC-13 · Elenco delle mie verifiche**
Dato che apro una mia classe e materia, quando consulto le verifiche, allora le vedo con titolo, stato, finestra di svolgimento e numero di studenti che l'hanno consegnata, in un elenco paginato.

**AC-14 · Correzione automatica delle domande chiuse**
Dato che uno studente consegna la verifica, quando la consegna viene salvata, allora il sistema calcola da solo il punteggio delle domande chiuse. Le domande aperte restano da correggere a mano, e il voto finale lo assegna il docente (DOC-03).

**AC-15 · Solo il docente della classe e materia**
Dato che sono autenticato come Studente, o come Docente su una classe o materia non mia, quando provo a creare, modificare o eliminare una verifica (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione. Lo studente non riceve mai le risposte corrette dall'API prima della chiusura.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Titolo | Sì | Testo, max 100 caratteri |
| Istruzioni | No | Testo, max 1000 caratteri |
| Classe e materia | Sì | Una coppia classe/materia assegnata al docente |
| Apertura e chiusura | Sì, per pubblicare | Chiusura successiva all'apertura |
| Durata massima | Sì, per pubblicare | In minuti, non più lunga della finestra *(proposta: max 180)* |
| Domande | Sì, per pubblicare | Almeno una |
| Punteggio per domanda | Sì | Numero intero maggiore di zero |

**Stati della verifica:** `bozza` → `programmata` → `aperta` → `chiusa`. Da `programmata` e `aperta` si può passare ad `annullata` (AC-10, AC-12).

- Il punteggio della verifica non è il voto: il voto lo assegna il docente in DOC-03, secondo la scala dei voti ancora da decidere.
- Con 412 studenti e il picco delle 9:00, molte verifiche possono aprirsi alla stessa ora (NFR-01).

## Fuori perimetro di questa storia

- Svolgimento della verifica e connessione che cade → **STU-02**
- Correzione delle domande aperte e assegnazione del voto → **DOC-03**
- Banca delle domande condivisa fra docenti *(da decidere)*
- Domande con allegati o immagini *(da decidere)*
- Ordine casuale di domande e opzioni per studente *(da decidere)*
- Tempi aggiuntivi per singoli studenti (es. studenti con DSA) *(da decidere)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Decisione aperta | Modifica di una verifica dopo lo svolgimento | Proposta in AC-10; una volta confermata va scritta come FR nel PRD |
| NFR | NFR-01 | Apertura della verifica nel picco |
| NFR | NFR-03 | Controllo ruolo e classe/materia lato backend; risposte corrette mai inviate allo studente (AC-15) |
| NFR | NFR-09 | Errori uniformi (AC-04, AC-06, AC-07) ed elenco verifiche paginato (AC-13) |
| Storia | DIR-04 | Le classi e materie su cui il docente può creare verifiche (AC-02) |
| Storia | DIR-01 | Docente disattivato: le sue verifiche restano (scenario "Docente che lascia la scuola") |
| Storia | STU-02 | Lo studente svolge la verifica creata qui |
| Storia | DOC-03 | Dalla verifica corretta si arriva al voto |

## Domande aperte per il team

1. Confermate la proposta sulla modifica dopo l'apertura (AC-10)? In alternativa la verifica diventa del tutto immodificabile, oppure si può modificare tutto ma chi l'ha già svolta la rifà.
2. Bastano i tre tipi di domanda (AC-03)? Servono anche domande con più risposte corrette o con una risposta numerica?
3. Il nuovo docente di una materia (DIR-04, AC-07) può correggere le verifiche lasciate dal precedente? *(proposta: sì, le vede e le corregge, ma restano a nome di chi le ha create)*
4. Lo studente vede il suo punteggio e le risposte corrette subito dopo la consegna, alla chiusura o solo quando il docente assegna il voto? *(proposta: alla chiusura)*
