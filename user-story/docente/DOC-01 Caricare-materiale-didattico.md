# DOC-01 · Caricare materiale didattico

**Ruolo:** Docente (ARC-002)

**Storia**

Come Docente, voglio caricare materiale didattico per le mie classi e materie, per permettere ai miei studenti di studiarlo quando e dove vogliono.

---

## Acceptance criteria della traccia

> 💡 Riportare qui gli AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Caricamento riuscito**
Dato che sono autenticato come Docente, quando carico un file indicando titolo, classe e materia, allora il materiale viene salvato e compare subito nell'elenco materiali di quella classe e materia, visibile agli studenti (STU-01).

**AC-02 · Solo le mie classi e materie**
Dato che sto caricando un materiale, quando scelgo classe e materia, allora posso scegliere solo fra le coppie classe/materia che il Direttore mi ha assegnato (DIR-04).

**AC-03 · Campi obbligatori**
Dato che sono nel modulo di caricamento, quando provo a salvare senza titolo, senza file o senza classe e materia, allora il sistema non salva il materiale e indica quali campi mancano.

**AC-04 · Formati ammessi**
Dato che scelgo un file da caricare, quando il formato non è fra quelli ammessi (vedi Regole e dati), allora il sistema rifiuta il file e mi dice quali formati sono accettati.

**AC-05 · Dimensione massima** *(proposta: 20 MB, da confermare con il team)*
Dato che scelgo un file più grande del limite, quando provo a caricarlo, allora il sistema lo rifiuta prima di inviarlo e mi indica il limite.

**AC-06 · Link esterno** *(proposta, da confermare con il team)*
Dato che voglio condividere un video o una pagina web, quando inserisco un link al posto del file, allora il materiale viene salvato come link e lo studente lo apre in una nuova scheda.

**AC-07 · Stessa materia in più classi**
Dato che insegno la stessa materia in più classi, quando carico un materiale, allora posso selezionare più classi insieme e il materiale compare in ognuna, senza doverlo caricare più volte.

**AC-08 · Modifica**
Dato che ho caricato un materiale, quando ne modifico titolo, descrizione o file e salvo, allora gli studenti vedono subito la versione aggiornata.

**AC-09 · Eliminazione**
Dato che ho caricato un materiale, quando lo elimino e confermo, allora non è più visibile agli studenti. Il sistema mi chiede conferma prima di eliminarlo.

**AC-10 · Elenco dei miei materiali**
Dato che apro una mia classe e materia, quando consulto i materiali, allora li vedo ordinati dal più recente, con titolo, data di caricamento e tipo, in un elenco paginato.

**AC-11 · Caricamento interrotto**
Dato che la connessione cade o lo storage dei file non risponde durante il caricamento, quando il caricamento fallisce, allora il materiale non viene salvato a metà, il sistema mi avvisa e i dati inseriti nel modulo restano, così posso riprovare.

**AC-12 · Materiale di chi non insegna più la materia**
Dato che il Direttore ha assegnato la materia della classe a un altro docente (DIR-04) o mi ha disattivato (DIR-01), quando uno studente apre i materiali, allora continua a vedere quelli che ho caricato; il nuovo docente può modificarli o eliminarli *(proposta, da confermare)*.

**AC-13 · Solo i docenti caricano materiale**
Dato che sono autenticato come Studente, quando provo a caricare, modificare o eliminare un materiale (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione. Lo stesso vale per un Docente che prova a farlo su una classe o materia non sua.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Titolo | Sì | Testo, max 100 caratteri |
| Descrizione | No | Testo, max 500 caratteri |
| File o link | Sì, uno dei due | File: PDF, DOCX, PPTX, XLSX, JPG, PNG, max 20 MB *(proposta)*. Link: URL valido http/https *(proposta)* |
| Classi | Sì | Almeno una, fra quelle in cui il docente insegna la materia scelta |
| Materia | Sì | Una sola, fra quelle assegnate al docente |

- Il materiale appartiene a una coppia classe/materia, non al docente: se cambia il docente, il materiale resta (AC-12).
- Data di caricamento e autore vengono registrati in automatico.
- Il file vive nello storage dei file, non nel database: nel database restano solo i metadati.

## Fuori perimetro di questa storia

- Consultazione del materiale da parte degli studenti → **STU-01**
- Cartelle o argomenti per organizzare il materiale *(da decidere: basta l'elenco per data?)*
- Pubblicazione programmata (materiale visibile da una certa data) *(da decidere)*
- Anteprima dei file nel browser (lo studente scarica o apre il file)

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| NFR | NFR-02 | HTTPS: i file viaggiano cifrati |
| NFR | NFR-03 | Controllo ruolo e classe/materia lato backend (AC-13) |
| NFR | NFR-09 | Errori uniformi (AC-03, AC-04, AC-05) ed elenco materiali paginato (AC-10) |
| Storia | DIR-04 | Le classi e materie su cui il docente può caricare (AC-02) |
| Storia | DIR-01 | Docente disattivato: il suo materiale resta (AC-12) |
| Storia | STU-01 | Lo studente consulta il materiale caricato qui |

## Domande aperte per il team

1. Il Direttore può caricare materiale? La tabella "Chi può fare cosa" del PRD dice di sì, DIR-03 dice che la sua vista è in sola lettura. *(proposta: no, carica solo il Docente)*
2. Confermate 20 MB come limite e l'elenco dei formati? Servono anche video caricati direttamente o bastano i link (AC-06)?
3. Chi può modificare il materiale di un docente che non insegna più quella materia (AC-12)? *(proposta: il nuovo docente della materia)*
4. Serve un limite di spazio totale per docente o per scuola? Pesa sui costi dello storage.
