# STU-02 · Svolgere una verifica

**Ruolo:** Studente (ARC-003)

**Storia**

Come Studente, voglio svolgere online le verifiche della mia classe, dall'iPad in classe o dal PC del laboratorio, per consegnarle senza fogli e senza il rischio di perdere le mie risposte.

---

## Acceptance criteria della traccia

> 💡 Riportare qui gli AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Elenco delle mie verifiche**
Dato che sono autenticato come Studente e iscritto a una classe, quando apro la sezione Verifiche, allora vedo le verifiche pubblicate per la mia classe con materia, titolo, finestra di svolgimento, durata e stato (programmata, da svolgere, in corso, consegnata, chiusa, non svolta, annullata), in un elenco paginato con quelle da svolgere in cima.

**AC-02 · Apertura solo nella finestra**
Dato che una verifica è programmata, quando provo ad aprirla prima dell'ora di apertura o dopo l'ora di chiusura, allora il sistema non me la fa iniziare e mi dice quando si apre o che è già chiusa. Prima dell'apertura non vedo le domande, neanche chiamando direttamente l'API.

**AC-03 · Inizio della verifica**
Dato che la verifica è aperta, quando premo "Inizia" e confermo, allora vedo le istruzioni e le domande, e parte il mio tempo. Il tempo a disposizione è la durata della verifica, ma finisce comunque all'ora di chiusura: se inizio tardi, ho meno tempo (vedi Regole e dati).

**AC-04 · Tempo rimanente**
Dato che sto svolgendo la verifica, quando la guardo, allora vedo sempre il tempo rimanente. Il tempo lo calcola il server, non il mio dispositivo: cambiare l'ora dell'iPad o ricaricare la pagina non lo modifica.

**AC-05 · Rispondere alle domande**
Dato che sto svolgendo la verifica, quando rispondo, allora per la risposta multipla scelgo una sola opzione, per il vero/falso scelgo vero o falso, per la risposta aperta scrivo un testo. Posso muovermi fra le domande in qualsiasi ordine e cambiare una risposta finché non consegno.

**AC-06 · Salvataggio automatico**
Dato che sto svolgendo la verifica, quando do o cambio una risposta, allora la risposta viene salvata subito sul server, senza premere nessun pulsante, e vedo un segno "salvato" accanto alla domanda.

**AC-07 · Consegna**
Dato che ho finito, quando premo "Consegna", allora il sistema mi mostra quante domande ho lasciato senza risposta e mi chiede conferma. Dopo la conferma la verifica risulta "consegnata", non posso più modificarla e vedo l'ora di consegna.

**AC-08 · Consegna automatica allo scadere del tempo**
Dato che il mio tempo finisce prima che io consegni, quando scade, allora il sistema consegna da solo le risposte salvate fino a quel momento e la segna come "consegnata automaticamente", così il docente lo sa.

**AC-09 · Un solo tentativo**
Dato che ho iniziato una verifica, quando provo a ricominciarla da capo, anche da un altro dispositivo, allora il sistema non crea un nuovo tentativo: riprendo quello già iniziato, con le risposte salvate e il tempo che resta.

**AC-10 · Connessione che cade** *(proposta per la decisione aperta, da confermare con il team)*
Dato che sto svolgendo la verifica e la connessione cade, quando succede, allora:
- vedo subito un avviso che sono offline e che le risposte non vengono salvate;
- posso continuare a rispondere: le risposte restano sul dispositivo e sono segnate "da salvare";
- il tempo continua a scorrere, perché lo conta il server (AC-04);
- quando la connessione torna, le risposte "da salvare" vengono inviate da sole e accettate se il mio tempo non è ancora scaduto;
- se il dispositivo si spegne o si blocca, riapro la verifica da un altro dispositivo e riprendo dalle ultime risposte salvate (AC-09).

**AC-11 · Tempo scaduto mentre sono offline** *(proposta, da confermare)*
Dato che la connessione è caduta e il mio tempo scade prima che torni, quando il sistema consegna in automatico (AC-08), allora valgono solo le risposte arrivate al server prima della scadenza. La consegna è segnata "consegnata automaticamente · connessione persa", così il docente può decidere se farmi recuperare la prova (DOC-03 AC-05).

**AC-12 · Risposte corrette non visibili durante la verifica**
Dato che sto svolgendo la verifica, quando la consulto o chiamo direttamente l'API, allora non ricevo mai le risposte corrette né i punteggi già calcolati (DOC-02 AC-15).

**AC-13 · Dopo la consegna** *(proposta, legata alla domanda aperta 4 di DOC-02)*
Dato che ho consegnato, quando riapro la verifica prima della chiusura, allora vedo solo le mie risposte. Dopo la chiusura vedo anche le risposte corrette e il punteggio delle domande chiuse. Il voto lo vedo quando il docente lo pubblica (DOC-03 AC-04, STU-03).

**AC-14 · Verifica non svolta**
Dato che non ho iniziato la verifica, quando arriva l'ora di chiusura, allora la verifica risulta "non svolta" e non posso più iniziarla (DOC-03 AC-08).

**AC-15 · Verifica modificata dal docente durante lo svolgimento** *(collegata a DOC-02 AC-10)*
Dato che sto svolgendo la verifica, quando il docente sposta più avanti l'ora di chiusura, annulla una domanda o annulla tutta la verifica, allora vedo l'avviso del cambiamento: la domanda annullata è segnata "non conta"; se la verifica è annullata, non posso più consegnarla e risulta "annullata".

**AC-16 · Usabile da iPad e PC** *(NFR-11)*
Dato che svolgo la verifica dall'iPad o dal PC del laboratorio, quando rispondo alle domande, allora la pagina si adatta allo schermo, in verticale e in orizzontale, e posso leggere le domande, scegliere le opzioni con il touch e scrivere le risposte aperte con la tastiera a schermo, senza zoomare né scorrere in orizzontale. Lo smartphone non è un dispositivo previsto per le verifiche: a scuola resta nell'armadietto (VIN-02).

**AC-17 · Solo le verifiche della mia classe**
Dato che sono autenticato come Studente, quando provo ad aprire, iniziare o consegnare una verifica di un'altra classe (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione. Lo stesso vale per un Docente o un Direttore che prova a svolgere una verifica.

---

## Regole e dati

| Dato | Regola |
| --- | --- |
| Inizio | Registrato dal server quando lo studente preme "Inizia" |
| Fine del tempo | Il primo fra: inizio + durata, oppure ora di chiusura della verifica |
| Risposta multipla | Una sola opzione fra quelle della domanda |
| Vero/falso | Vero o falso |
| Risposta aperta | Testo, max 2000 caratteri *(proposta)* |
| Consegna | Manuale (AC-07) o automatica (AC-08, AC-11), con data e ora del server |

**Stati della verifica per lo studente:** `programmata` → `da svolgere` → `in corso` → `consegnata` (o `consegnata automaticamente`). Se non la inizia: `non svolta`. In ogni momento il docente può portarla ad `annullata` (DOC-02 AC-10).

- Fa fede solo l'ora del server: inizio, tempo rimanente e consegna non dipendono dall'orologio del dispositivo.
- Le verifiche si svolgono a scuola, sull'iPad o sul PC del laboratorio. Se un dispositivo si spegne, lo studente riprende da un iPad di riserva o da un PC (AC-09, AC-10).
- Ogni risposta è salvata appena data (AC-06): una connessione che cade fa perdere al massimo le risposte date mentre si è offline, e solo se la connessione non torna prima della fine del tempo.
- Alla consegna il sistema corregge da solo le domande chiuse (DOC-02 AC-14).
- Ordine di grandezza: al picco delle 9:00 più classi iniziano insieme; ogni studente salva una risposta ogni pochi secondi. Con 100 studenti in verifica sono circa 20-50 salvataggi al secondo (NFR-01).

## Fuori perimetro di questa storia

- Creazione della verifica e modifiche del docente → **DOC-02**
- Correzione delle domande aperte e voto → **DOC-03**
- Consultazione del voto → **STU-03**
- Controlli anti-copiatura (blocco del cambio scheda, webcam, ordine casuale per studente) *(da decidere)*
- Tempi aggiuntivi per singoli studenti (es. studenti con DSA) *(da decidere, vedi DOC-02)*
- Svolgimento completamente offline (verifica scaricata prima e consegnata dopo)

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Decisione aperta | Connessione che cade durante una verifica | Proposta in AC-10 e AC-11; una volta confermata va scritta come FR nel PRD |
| NFR | NFR-01 | Apertura della verifica e salvataggio delle risposte nel picco delle 9:00 |
| NFR | NFR-02 | HTTPS: le risposte viaggiano cifrate |
| NFR | NFR-03 | Controllo ruolo e classe lato backend; risposte corrette mai inviate prima della chiusura (AC-12, AC-17) |
| NFR | NFR-09 | Elenco verifiche paginato (AC-01) ed errori uniformi (AC-02, AC-09, AC-17) |
| NFR | NFR-11 | Usabile da iPad e PC (AC-16) |
| Storia | DOC-02 | La verifica svolta qui; modifiche dopo l'apertura (AC-15) |
| Storia | DOC-03 | Consegna, verifica non svolta e recupero (AC-08, AC-11, AC-14) |
| Storia | STU-03 | Il voto della verifica |

## Domande aperte per il team

1. Confermate la proposta sulla connessione che cade (AC-10, AC-11)? In alternativa: il tempo si ferma mentre si è offline (più giusto per lo studente, ma facile da sfruttare staccando il Wi-Fi), oppure il docente può dare a mano qualche minuto in più a un singolo studente.
2. Va bene che il tempo finisca comunque all'ora di chiusura, anche per chi inizia tardi (AC-03)?
3. Quando lo studente vede risposte corrette e punteggio (AC-13)? *(proposta: alla chiusura, come in DOC-02)*
4. Serve un NFR sul salvataggio delle risposte, per esempio "nessuna risposta salvata va persa, anche se il backend si riavvia durante una verifica"?
5. Lo studente può aprire la stessa verifica su due dispositivi insieme (AC-09)? *(proposta: sì, ma vale l'ultima risposta salvata per ogni domanda)*
6. La scuola ha iPad di riserva per chi resta senza batteria durante una verifica, o si passa ai PC del laboratorio?
