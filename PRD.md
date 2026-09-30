# PRD di ScuolaChill · Team Regeestro

> 💡 **Come usare questo template**
>
> Duplica questa pagina e compilala con il tuo team. Dove trovi del testo in *corsivo*, sostituiscilo con il vostro. I callout 💡 sono consigli per te: cancellali prima della consegna da questo markdown.
>
> Il documento ha due parti. Nella prima scrivi **cosa** fa ScuolaChill, nella seconda **come** lo costruirai. Tienile separate. Chi legge la prima parte deve capire tutto senza sapere cos'è Spring Boot.
>
> Un buon PRD sta fra le 15 e le 25 pagine. Se ne scrivi di più, probabilmente stai descrivendo invece di decidere.

---

## Informazioni sul documento

| | |
| --- | --- |
| **Prodotto** | ScuolaChill |
| **Team** | Regeestro |
| **Autori** | Daniele Costantini |
| **Versione** | 0.0.9 |
| **Data** | 23/09/2026 |
| **Stato** | Bozza |

### Storico delle versioni

| Versione | Data | Autore | Cosa è cambiato e perché |
| --- | --- | --- | --- |
| 0 | 23/09/2026 | Daniele Costantini | Prima stesura |
| 0.0.1 | 25/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DIR-01 e la decisione FR-EXT-01 sul fallimento dell'email |
| 0.0.2 | 25/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DIR-02 |
| 0.0.3 | 25/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DIR-03 |
| 0.0.4 | 25/09/2026 | Daniele Costantini | Numerazione allineata alla traccia: DIR-03 è "Vedere tutto", DIR-04 è "Creare classi e comporle" |
| 0.0.5 | 25/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DIR-04 |
| 0.0.6 | 25/09/2026 | Daniele Costantini | Storie del Direttore: aggiunti modifica, riattivazione e password dimenticata (DIR-01, DIR-02); user flow e scenari di DIR-01, DIR-02, DIR-04; NFR-04 e NFR-10; permessi del Direttore |
| 0.0.7 | 30/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DOC-01; user flow e scenari di DOC-01 |
| 0.0.8 | 30/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DOC-02, con la proposta sulla modifica di una verifica dopo lo svolgimento (AC-10); user flow e scenari di DOC-02 |
| 0.0.9 | 30/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DOC-03, con la proposta sulla scala dei voti (AC-01); user flow e scenari di DOC-03 |

> 💡 Il PRD cambierà durante l'anno. Ogni modifica va registrata qui, con la sua ragione. Un PRD che dice una cosa mentre il codice ne fa un'altra è peggio di nessun PRD.

---

# Prima parte · Il cosa

## Scopo e perimetro

### Perché esiste ScuolaChill

**Dal lato business.** *Quale problema risolve, e per chi. Due o tre frasi.*

**Dal lato tecnico.** *Cosa copre il sistema, in grandi linee. Due o tre frasi.*

### Cosa è incluso

- Creazione e gestione degli account di docenti e studenti da parte del Direttore
- Creazione delle classi e loro composizione (assegnazione studenti, docenti e materie)
- Caricamento e consultazione del materiale didattico per materia e classe
- Creazione e svolgimento delle verifiche
- Assegnazione e consultazione dei voti, raggruppati per materia
- Vista d'insieme del Direttore su classi, docenti, studenti e andamento dei voti
- Autenticazione e autorizzazione basata sui tre ruoli (Direttore, Docente, Studente)

### Cosa non è incluso

- Gestione delle assenze
- Comunicazioni con le famiglie
- Gestione amministrativa/contabile della scuola (rette, pagamenti)
- Orario delle lezioni (timetabling)
- Messaggistica diretta fra utenti (chat)

> ⚠️ *Questa lista deriva da ciò che la traccia NON menziona fra le funzionalità richieste. Verificatela con il team: se avete in mente di aggiungere qualcosa di più, va spostato sopra, fra "cosa è incluso".*

> 💡 La lista di cosa **non** è incluso è la più preziosa del documento. Ogni riga qui ti evita una settimana di discussioni più avanti.

---

## Stakeholder

| Stakeholder | Cosa fa | Cosa gli interessa | Come lo coinvolgete |
|---|---|---|---|
| Direttore | Dirige la scuola: crea account e classi, supervisiona tutto | Una vista d'insieme affidabile e rapida, senza dover entrare in ogni singola pagina | Intervista, collaudo finale |
| Docenti | Carica materiale, crea verifiche, assegna voti sulle proprie classi/materie | Uno strumento semplice da usare ogni giorno, con dati corretti sui propri studenti | Collaudo |
| Studenti | Consulta materiale, svolge verifiche, controlla i propri voti | Un'app semplice, veloce, usabile anche da smartphone | Collaudo diretto (ragazzi del primo anno) |
| Docente del corso | Valida il PRD | Che le scelte tecniche e di prodotto siano motivate e coerenti | Presentazione e domande |
| Collaudatori del primo anno | Usano ScuolaChill come utenti reali (impersonano Direttore, docente, studenti) | Un prodotto che funzioni davvero, non solo in demo | Intervista, collaudo |
| *Altri? (es. sponsor del progetto, docente/i di riferimento)* | *…* | *…* | *…* |

> 💡 Gli stakeholder non sono solo gli utenti. Sono anche chi approva, chi paga, chi manterrà il sistema. Chiediti chi resterebbe deluso se ScuolaChill non funzionasse.

---

## Destinatari e contesto d'uso

### La scuola che avete immaginato

*Descrivi la scuola per cui progettate. Che tipo di istituto è, dove si trova, come si organizza la giornata. Questi dati tornano nella stima del carico, quindi scegli numeri che poi userai davvero.*

| | Valore |
| --- | --- |
| Numero di studenti | 484 |
| Numero di docenti | 18 |
| Numero di classi | 21 |
| Orario scolastico | Lunedì, Mercoledì e Venerdì 8:10 - 13:20 Martedì e Giovedì 8:10 - 16:10 |
| Connettività | *es. Wi-Fi scolastico condiviso, rete mobile degli studenti, …* |

### Gli archetipi

Arricchisci gli archetipi della traccia.

| ID | Archetipo | Contesto d'uso | Competenze digitali | Dispositivo principale | Frequenza d'uso |
| --- | --- | --- | --- | --- | --- |
| ARC-001 | Direttore — dirige la scuola, ha poco tempo, gli serve la visione d'insieme; è l'unico che gestisce anagrafiche e classi | Ufficio, sessioni brevi e mirate | *Ipotesi: medio-basse — serve un'interfaccia semplice, poche azioni per completare un task* | PC/laptop | Quotidiana, ma per sessioni brevi |
| ARC-002 | Docente — insegna una o più materie in una o più classi; prepara verifiche, carica materiale, valuta gli studenti | Aula, sala professori, casa (preparazione materiale) | *Ipotesi: medie* | PC/laptop, occasionalmente tablet | Quotidiana |
| ARC-003 | Studente — iscritto a una classe; studia sul materiale dei docenti, svolge le verifiche, tiene d'occhio i propri voti | Aula durante le verifiche, casa per lo studio | *Ipotesi: alte (nativi digitali)* | Smartphone per consultazione, PC/laptop probabile per le verifiche | Quotidiana, più volte al giorno |

> ⚠️ *Le colonne "Competenze digitali", "Dispositivo principale" e "Frequenza d'uso" sono ipotesi di partenza: vanno confermate (o corrette) con l'intervista ai ragazzi del primo anno prevista più sotto, prima di chiudere la sezione.*

> 💡 I collaudatori veri sono i ragazzi del primo anno. Usano lo smartphone in corridoio o il PC in laboratorio? La risposta cambia l'interfaccia, i requisiti di usabilità e perfino il dimensionamento.

---

## Panoramica e casi d'uso

### ScuolaChill in poche righe

ScuolaChill è il registro della scuola, ma online e tutto in un posto.

Lei crea gli account di docenti e studenti e forma le classi. Poi ognuno fa la sua parte: i docenti caricano il materiale, preparano le verifiche e danno i voti; gli studenti studiano, fanno le verifiche anche dal telefono e vedono subito i propri voti, materia per materia.

E lei, da una sola pagina, vede come vanno tutte le classi, senza dover chiedere a nessuno.

Assenze, comunicazioni con le famiglie e orario restano fuori: ci concentriamo sulla didattica di ogni giorno.

### User flow e scenari

Per ogni ruolo, scegli **almeno tre** storie principali e descrivi il percorso completo.

**Storia:** DIR-01 Creare account docente

**User flow**

1. Il Direttore accede a ScuolaChill
2. Apre la sezione crea utente e sceglie "Docente"
3. Inserisce nome, cognome, email e le materie che il docente può insegnare
4. Viene mandata una mail con le credenziali al docente
5. Al primo accesso il docente imposta una nuova password e l'account diventa attivo

**Scenario principale.** A inizio settembre è arrivata una nuova docente di matematica, la prof.ssa Giulia Neri. Il Direttore apre ScuolaChill dal PC dell'ufficio, inserisce nome, cognome ed email e sceglie "Matematica" e "Fisica" dall'elenco materie. Dopo il salvataggio la docente compare nell'elenco come "in attesa di attivazione". Il giorno dopo la prof.ssa Neri apre l'email, accede, imposta la sua password e il suo account risulta "attivo". Il Direttore poi la assegna alle classi (DIR-04).

**Scenari alternativi.**
- *Email già registrata:* il Direttore sbaglia e inserisce l'email di un altro docente. Il sistema non salva e gli dice che l'email è già in uso.
- *Email non partita:* il servizio email non risponde. L'account viene salvato lo stesso, il Direttore vede un avviso e più tardi reinvia le credenziali dall'elenco docenti (FR-EXT-01).
- *Docente che lascia la scuola:* a fine anno il Direttore disattiva l'account. Il docente non può più accedere, ma le verifiche e i voti che ha dato restano.

**Storia:** DIR-02 Creare account studente

**User flow**

1. Il Direttore accede a ScuolaChill
2. Apre la sezione crea utente e sceglie "Studente"
3. Inserisce nome, cognome, email e, se esiste già, la classe
4. Viene mandata una mail con le credenziali allo studente
5. Al primo accesso lo studente imposta una nuova password e l'account diventa attivo

**Scenario principale.** Durante l'anno arriva un nuovo studente, Luca Galli, che va in 2B. Il Direttore lo crea inserendo i suoi dati e sceglie la classe 2B. Luca riceve l'email, accede dal telefono, cambia la password e trova subito il materiale e le verifiche della 2B.

**Scenari alternativi.**
- *Classe non ancora creata:* a inizio anno le classi non esistono ancora. Il Direttore crea gli studenti senza classe e li assegna dopo (DIR-04); la vista d'insieme glieli segnala come "studenti senza classe".
- *Email non partita:* come per i docenti, l'account resta salvato e il Direttore reinvia le credenziali (FR-EXT-01).
- *Password dimenticata:* lo studente la reimposta da solo dalla pagina di accesso, senza chiedere al Direttore *(proposta, da confermare)*.

**Storia:** DIR-04 Creare classi e comporle

**User flow**

1. Il Direttore accede a ScuolaChill
2. Apre la sezione Classi e crea una classe con nome e anno scolastico
3. Aggiunge gli studenti scegliendoli fra quelli senza classe
4. Aggiunge le materie e per ognuna sceglie il docente
5. Controlla il riepilogo della classe: nessuna materia deve restare senza docente

**Scenario principale.** Prima dell'inizio delle lezioni il Direttore prepara la 1A. La crea per l'anno 2026/2027, seleziona i 23 studenti iscritti fra quelli senza classe, aggiunge Italiano, Matematica e Inglese e per ciascuna sceglie il docente fra quelli abilitati. Il riepilogo non mostra avvisi: da quel momento studenti e docenti vedono la 1A fra le proprie classi.

**Scenari alternativi.**
- *Studente già in un'altra classe:* il sistema non lo iscrive due volte e propone il trasferimento; i voti già presi restano nello storico con la classe di origine *(proposta, da confermare)*.
- *Nessun docente per una materia:* il Direttore salva comunque la classe; la materia resta evidenziata e compare fra le segnalazioni della vista d'insieme (DIR-03).
- *Classe creata per errore:* il Direttore la elimina; se però contiene già studenti o voti, il sistema glielo impedisce e spiega il motivo.

**Storia:** DOC-01 Caricare materiale didattico

**User flow**

1. Il Docente accede a ScuolaChill
2. Apre una sua classe e materia e sceglie "Carica materiale"
3. Inserisce il titolo e, se vuole, una descrizione
4. Sceglie il file (o incolla un link) e, se insegna la stessa materia in altre classi, le aggiunge
5. Salva: il materiale compare nell'elenco e gli studenti lo vedono subito

**Scenario principale.** La domenica sera la prof.ssa Neri prepara la lezione di lunedì sulle equazioni di secondo grado. Da casa apre ScuolaChill, entra in 2B · Matematica, carica il PDF con gli esercizi e seleziona anche la 2C, dove insegna la stessa materia. Lunedì mattina gli studenti delle due classi trovano il materiale in cima all'elenco.

**Scenari alternativi.**
- *File troppo grande o formato non ammesso:* il sistema rifiuta il file prima di inviarlo e dice qual è il limite o quali formati sono accettati.
- *Connessione che cade durante il caricamento:* il materiale non viene salvato a metà; la docente vede un avviso e riprova senza reinserire titolo e classi.
- *Cambio di docente:* a metà anno il Direttore assegna Matematica della 2B a un altro docente. Gli studenti continuano a vedere i materiali della prof.ssa Neri *(proposta, da confermare)*.

**Storia:** DOC-02 Creare le proprie verifiche

**User flow**

1. Il Docente accede a ScuolaChill
2. Apre una sua classe e materia e sceglie "Nuova verifica"
3. Inserisce titolo e istruzioni e aggiunge le domande, con punteggio e risposta corretta
4. Imposta apertura, chiusura e durata e controlla l'anteprima
5. Pubblica: gli studenti vedono la verifica in elenco e possono aprirla dall'ora di apertura

**Scenario principale.** Il mercoledì pomeriggio la prof.ssa Neri prepara la verifica sulle equazioni di secondo grado per la 2B. Crea 8 domande a risposta multipla e 2 aperte, imposta l'apertura venerdì alle 9:00, la chiusura alle 10:00 e una durata di 50 minuti. Dall'anteprima si accorge di un'opzione ripetuta, la corregge e pubblica. Venerdì alle 9:00 gli studenti la aprono dal laboratorio; alla consegna le domande chiuse sono già corrette e a lei restano solo le due aperte.

**Scenari alternativi.**
- *Errore scoperto durante la verifica:* a verifica aperta la docente nota che una domanda ha la risposta corretta sbagliata. Non può più modificarla, ma la annulla: non conta per nessuno e i punteggi si ricalcolano *(proposta, da confermare)*.
- *Laboratorio occupato:* la verifica è programmata ma il laboratorio non è disponibile. Prima dell'apertura la docente sposta la finestra al lunedì senza perdere nulla.
- *Stessa verifica in un'altra classe:* per la 2C la docente duplica la verifica, cambia la classe e la finestra e la pubblica.

**Storia:** DOC-03 Assegnare i voti

**User flow**

1. Il Docente accede a ScuolaChill
2. Apre una sua classe e materia e sceglie la verifica chiusa da valutare
3. Per ogni studente controlla il punteggio delle domande chiuse e corregge quelle aperte
4. Accetta o cambia il voto proposto e, se vuole, aggiunge un commento
5. Pubblica i voti: ogni studente vede il suo

**Scenario principale.** Il sabato mattina la prof.ssa Neri apre la verifica della 2B chiusa venerdì. Le domande a risposta multipla sono già corrette; lei legge le due aperte di ogni studente e assegna i punti. Per Luca Galli il sistema propone 7, lei lo lascia così e aggiunge "Bene il procedimento, attenzione ai segni". Finito l'ultimo studente pubblica i voti, e Luca li vede dal telefono pochi minuti dopo.

**Scenari alternativi.**
- *Interrogazione:* il lunedì la docente interroga due studenti e inserisce subito i due voti orali; gli studenti li vedono in giornata.
- *Studente assente:* uno studente non ha svolto la verifica e risulta "non svolta". La recupera su carta la settimana dopo e la docente gli inserisce il voto a mano.
- *Voto sbagliato:* la docente si accorge di aver dato 5 invece di 6,5. Lo corregge; lo studente vede il voto nuovo e il sistema tiene traccia del cambio.

*Ripeti il blocco per le altre storie principali di Docente e Studente.*

---

## Requisiti funzionali

### Le user story della traccia

| ID | Storia | AC aggiunti dal team | Note |
| --- | --- | --- | --- |
| DIR-01 | Creare account docente | AC-05 campi obbligatori e formato; AC-06 materie scelte da elenco predefinito; AC-07 cambio password obbligatorio al primo accesso; AC-08 invio email fallito; AC-09 solo il Direttore può creare docenti; AC-10 modifica dei dati; AC-11 riattivazione; AC-12 password dimenticata *(proposta)* (dettaglio in `user-story/DIR-01`) | Collegata a FR-EXT-01 (fallimento email). L'assegnazione del docente alle classi è in DIR-04. Gli account non si eliminano, si disattivano |
| DIR-02 | Creare account studente | AC-01…AC-03 creazione, email unica, campi obbligatori; AC-04 classe facoltativa alla creazione; AC-05/AC-06 stato "in attesa di attivazione" e cambio password al primo accesso; AC-07 invio email fallito; AC-08 disattivazione; AC-09 solo il Direttore può creare studenti; AC-10 creazione da CSV *(da confermare)*; AC-11 modifica dei dati; AC-12 riattivazione; AC-13 password dimenticata *(proposta)* (dettaglio in `user-story/DIR-02`) | Collegata a FR-EXT-01 (fallimento email) e a DIR-04 (composizione e trasferimento fra classi). Stessi stati account di DIR-01 |
| DIR-03 | Vedere tutto | AC-01 riepilogo in prima pagina; AC-02 segnalazioni da sistemare; AC-03…AC-06 elenco e dettaglio di classi, studenti e docenti; AC-07 andamento dei voti per classe, materia e periodo; AC-08 ricerca; AC-09 elenchi paginati e filtrabili; AC-10 sola lettura; AC-11 nessun dato; AC-12 solo il Direttore (dettaglio in `user-story/DIR-03`) | Le medie dipendono dalla decisione sulla scala dei voti (DOC-03). Collegata a NFR-04 (usabilità) e NFR-10 (prestazioni) |
| DIR-04 | Creare classi e comporle | AC-01/AC-02 creazione classe con nome unico per anno scolastico; AC-03/AC-04 aggiunta studenti, uno studente in una sola classe; AC-05…AC-07 materie con un docente abilitato per materia; AC-08 trasferimento *(proposta)*; AC-09 rimozione studente; AC-10 eliminazione solo di classi vuote; AC-11 riepilogo della classe; AC-12 solo il Direttore (dettaglio in `user-story/DIR-04`) | Collegata alla decisione aperta sul trasferimento fra classi: proposta in AC-08, da confermare e poi scrivere come FR |
| DOC-01 | Caricare materiale didattico | AC-01 caricamento con titolo, classe e materia; AC-02 solo le proprie classi e materie; AC-03 campi obbligatori; AC-04 formati ammessi; AC-05 dimensione massima *(proposta 20 MB)*; AC-06 link esterno *(proposta)*; AC-07 stessa materia in più classi; AC-08 modifica; AC-09 eliminazione; AC-10 elenco paginato; AC-11 caricamento interrotto; AC-12 materiale di chi non insegna più la materia *(proposta)*; AC-13 solo il docente della classe e materia (dettaglio in `user-story/docente/DOC-01`) | Il materiale appartiene alla coppia classe/materia, non al docente. Collegata a DIR-04 e STU-01. Da chiarire se il Direttore può caricare materiale |
| DOC-02 | Creare le proprie verifiche | AC-01 creazione in bozza; AC-02 solo le proprie classi e materie; AC-03/AC-04 tipi di domanda (multipla, vero/falso, aperta) con punteggio e risposta corretta; AC-05 ordine delle domande; AC-06 finestra di svolgimento e durata; AC-07 pubblicazione; AC-08 anteprima; AC-09 modifica prima dell'apertura; AC-10 modifica dopo l'apertura *(proposta)*; AC-11 duplicazione; AC-12 eliminazione; AC-13 elenco paginato; AC-14 correzione automatica delle domande chiuse; AC-15 solo il docente della classe e materia (dettaglio in `user-story/docente/DOC-02`) | Collegata alla decisione aperta sulla modifica dopo lo svolgimento: proposta in AC-10, da confermare e poi scrivere come FR. Il punteggio non è il voto (DOC-03) |
| DOC-03 | Assegnare i voti | AC-01 scala da 1 a 10 con passo 0,5 *(proposta)*; AC-02 correzione della verifica online; AC-03 voto proposto dal punteggio *(proposta)*; AC-04 pubblicazione dei voti di una verifica; AC-05 voto per prove fuori da ScuolaChill (scritto, orale, pratico); AC-06 voti a tutta la classe; AC-07 solo le proprie classi e materie; AC-08 verifica non svolta; AC-09 commento; AC-10 modifica con storico; AC-11 eliminazione con storico; AC-12 voti per quadrimestre *(proposta)*; AC-13 registro della classe; AC-14 solo il docente della classe e materia (dettaglio in `user-story/docente/DOC-03`) | Collegata alla decisione aperta sulla scala dei voti: proposta in AC-01, da confermare e poi scrivere come FR. Le medie di DIR-03 e STU-03 dipendono da qui |
| STU-01 | Consultare il materiale didattico | *…* | *…* |
| STU-02 | Svolgere una verifica | *…* | *Collegata alla decisione aperta sulla connessione che cade* |
| STU-03 | Consultare i propri voti | *…* | *…* |

> 💡 Gli AC completi (già scritti nella traccia) restano nel documento della traccia stessa come riferimento; qui riportate solo quelli che il team **aggiunge**.

> 💡 Gli acceptance criteria della traccia sono il minimo. Puoi aggiungerne, non toglierne. Scrivi quelli nuovi nello stesso formato *Dato che / Quando / Allora*.

### Le decisioni lasciate aperte dalla traccia

La traccia lascia alcune scelte a te. Ognuna diventa un requisito con il suo ID. Usa questo formato.

> **FR-[AREA]-[NN] · [Titolo]** (collegato a *ID della storia*)
> *Cosa avete deciso, in modo verificabile. Motivazione: perché avete scelto così.*

I punti che devi decidere almeno sono questi.

- [ ] La scala dei voti (DOC-03). Da quanto a quanto, con quale passo, se ammette segni come "+" e "−".
- [ ] Il trasferimento di uno studente fra classi (DIR-04). Si può fare? Cosa succede ai voti?
- [ ] La modifica di una verifica dopo lo svolgimento (DOC-02).
- [ ] La connessione che cade durante una verifica (STU-02).
- [x] Il fallimento del servizio esterno (per esempio l'email delle credenziali).
- [ ] *Altre decisioni che il team ha scoperto*

> **FR-EXT-01 · Fallimento del servizio email delle credenziali** (collegato a DIR-01, DIR-02)
> Se l'invio dell'email con le credenziali fallisce, l'account viene comunque creato nello stato "in attesa di attivazione". Il Direttore vede subito un avviso che l'email non è partita e può richiedere un nuovo invio dall'elenco utenti. Motivazione: un disservizio temporaneo del provider email non deve bloccare il lavoro del Direttore né fargli reinserire i dati.

> 📌 **Cosa resta davvero da decidere voi (non pre-compilabile dalla traccia):**
> - Le assunzioni sulla scuola (numero studenti/docenti/classi, orario, connettività)
> - Lo stack tecnologico e l'infrastruttura cloud, con alternative motivate
> - La stima del carico, il dimensionamento delle macchine e i costi mensili
> - Le 5 decisioni aperte elencate sopra (scala voti, trasferimento classi, modifica verifica, connessione che cade, fallimento servizio esterno)
> - User flow e scenari per le storie principali di ogni ruolo
> - Diagrammi (architettura, ER) e il contratto delle API principali
> - Design pattern e organizzazione del codice
>
> Se vuoi, possiamo affrontarli uno alla volta: dimmi da dove preferisci partire (es. stima della scuola, oppure stack tecnologico) e ti aiuto a ragionarci — senza sostituirmi al vostro brain dump iniziale, come raccomanda la nota del prof.

---

## Requisiti non funzionali

Ogni requisito ha una soglia, una condizione e un modo per verificarlo. Ed è collegato ad almeno una user story.

| ID | Famiglia | Requisito | Soglia e condizione | Come si verifica | Storie collegate |
| --- | --- | --- | --- | --- | --- |
| NFR-01 | Prestazioni | *es. Apertura della verifica nel picco* | *es. meno di 2 s per il 95% delle richieste, 75 utenti nello stesso minuto — da tarare sulla vostra stima di carico* | *Test di carico* | STU-02 |
| NFR-02 | Sicurezza | Tutto il traffico fra frontend e backend viaggia su HTTPS | Nessuna chiamata in chiaro, certificato valido | Ispezione del traffico / certificato | Tutte |
| NFR-03 | Sicurezza | Il controllo dei ruoli (Direttore/Docente/Studente) è applicato lato backend su ogni endpoint | Ogni chiamata API verifica il ruolo indipendentemente dal frontend | Test con Postman usando token di ruoli diversi | Tutte |
| NFR-04 | Usabilità | Dalla vista d'insieme il Direttore raggiunge la pagina che risolve una segnalazione (studente senza classe, materia senza docente, email non partita) con un solo click | 1 click da ogni segnalazione, senza passare da menu intermedi | Prova con un collaudatore nel ruolo di Direttore | DIR-03, DIR-04 |
| NFR-05 | Disponibilità | Il sistema è deployato sull'infrastruttura cloud scelta e raggiungibile pubblicamente | Uptime minimo durante il periodo di collaudo (da definire, es. 99%) | Monitoraggio / test di raggiungibilità | Tutte |
| NFR-06 | Ambientale | *…da definire — es. dimensionamento minimo per contenere i costi cloud entro il budget* | *…* | *…* | *…* |
| NFR-07 | Supporto | L'applicazione gira in due configurazioni separate, Development e Production, senza segreti nel codice sorgente | Segreti gestiti tramite variabili d'ambiente / secret manager | Revisione della configurazione e del repository | *Trasversale* |
| NFR-08 | Interazione | Le API principali sono documentate con OpenAPI/Swagger e verificate con una collezione Postman | Copertura di tutte le route CRUD principali | Revisione Swagger + esecuzione della collezione Postman | Tutte |
| NFR-09 | Conformità | Gli elenchi (studenti, materiali, voti) sono paginati e le risposte di errore hanno un formato uniforme con codici HTTP coerenti | Paginazione su ogni collezione, schema di errore unico su tutta l'API | Test automatici sulle risposte | DIR-03, STU-01, STU-03 |
| NFR-10 | Prestazioni | La vista d'insieme del Direttore (riepilogo, segnalazioni, medie) si apre rapidamente anche con tutta la scuola caricata | Meno di 2 s per il 95% delle aperture, con 484 studenti, 21 classi e un quadrimestre di voti — *da tarare sulla stima di carico* | Test di carico su dati di prova della dimensione della scuola | DIR-03 |

> 💡 Le famiglie da coprire sono queste. **Prestazioni, disponibilità, scalabilità, sicurezza** e **conformità** vengono dalla lezione sui requisiti funzionali e non funzionali. **Usabilità, ambientali, supporto** e **interazione** vengono dalla lezione sul PRD. Se una famiglia resta vuota, scrivi perché non vi riguarda.
>
> I requisiti trasversali della traccia (HTTPS, paginazione, OpenAPI, errori uniformi, Dev e Prod) sono già obbligatori. Riportali qui con il loro ID.

### Requisiti impliciti

Prima di chiudere questa sezione, intervista per dieci minuti un ragazzo del primo anno. La domanda è una sola. *"Cosa daresti per scontato che un'app di questo tipo faccia sempre, o non faccia mai?"*

| Chi avete intervistato | Cosa ha detto | Requisito che ne avete ricavato |
| --- | --- | --- |
| *nome o iniziali* | *"Il voto non deve sparire, mai"* | *NFR-…* |
| | | |

---

## Assunzioni, vincoli e dipendenze

### Assunzioni

Quello che date per vero senza poterlo garantire.

| ID | Assunzione | Cosa succede se è falsa |
| --- | --- | --- |
| ASS-01 | La scuola ha 484 studenti e 18 docenti | Il dimensionamento va rifatto |
| | | |

### Vincoli

I limiti che non potete cambiare.

| ID | Vincolo | Da dove viene |
| --- | --- | --- |
| VIN-01 | *es. Il budget cloud è quello dei crediti studente* | *Traccia del progetto* |
| | | |

### Dipendenze

Le cose esterne senza cui non potete andare avanti.

| ID | Dipendenza | Serve entro | Chi se ne occupa |
| --- | --- | --- | --- |
| DIP-01 | Account attivo sul servizio email per l'invio delle credenziali (DIR-01, DIR-02) | Prima del collaudo | *nome* |
| | | | |

# Seconda parte · Il come

<aside>
💡

Da qui in poi parli al tuo docente e al tuo team, non al Direttore. Ogni scelta tecnica va motivata e confrontata con almeno un'alternativa. "Lo conosciamo" è una motivazione valida, ma non può essere l'unica.

</aside>

## Stima del carico

### Utenti concorrenti

| Situazione | Utenti concorrenti | Da dove viene il numero |
| --- | --- | --- |
| Uso normale durante la giornata | *…* | *…* |
| Picco delle 9:00 (verifiche) | 100 | *…* |
| Fine quadrimestre (voti) | 350 | *…* |

### Profilo di carico

| Operazione | Frequente? | Pesante? | Critica? | Note |
| --- | --- | --- | --- | --- |
| Login | *…* | *…* | *…* | *…* |
| Apertura verifica | *…* | *…* | *…* | *…* |
| Consegna verifica | *…* | *…* | *…* | *…* |
| Dashboard del Direttore | *…* | *…* | *…* | *…* |
| Caricamento materiale | *…* | *…* | *…* | *…* |

<aside>
💡

I numeri di qui devono essere coerenti con la scuola che avete immaginato e con i requisiti non funzionali. Se dichiarate 800 studenti, non potete dimensionare per 20 utenti senza spiegare perché.

</aside>

---

## Scelte tecnologiche

| Area | Scelta | Alternativa considerata | Perché avete scelto così |
| --- | --- | --- | --- |
| Backend | *…* | *…* | *…* |
| Frontend | *…* | *…* | *…* |
| Database | *…* | *…* | *…* |
| Provider cloud | *…* | *…* | *…* |
| Servizi cloud | *…* | *…* | *…* |
| Regione | *…* | *…* | *…* |
| Servizio esterno | *…* | *…* | *…* |

---

## Architettura

### Diagramma dei componenti

*Inserisci qui il diagramma. Deve mostrare i componenti principali e come comunicano.*

### I livelli

| Livello | Cosa fa in ScuolaChill | Esempio concreto |
| --- | --- | --- |
| Presentation / API | *…* | *…* |
| Application / Business | *…* | *…* |
| Data access | *…* | *…* |

### Le dipendenze fra i livelli

*Chi può conoscere chi, e in quale direzione. Spiega come questa struttura riduce l'accoppiamento e rende il sistema testabile.*

---

## Le API

### Le risorse

*Elenca le risorse REST principali. Es. `/classi`, `/verifiche`, `/voti`.*

### Il contratto delle API principali

| Verbo | Route | Chi può chiamarla | Payload di esempio | Risposte previste |
| --- | --- | --- | --- | --- |
| `POST` | `/api/docenti` | Direttore | `{ "nome": "Mario", "cognome": "Rossi", "email": "m.rossi@…", "materieIds": [1, 3] }` | 201 creato, 400 dati non validi, 403 ruolo non autorizzato, 409 email già registrata |
| `GET` | *…* | *…* | *…* | *…* |
| `PUT` | *…* | *…* | *…* | *…* |
| `PATCH` | *…* | *…* | *…* | *…* |
| `DELETE` | *…* | *…* | *…* | *…* |

### Errori, validazione e paginazione

**Formato uniforme degli errori.** *Mostra un esempio di risposta di errore.*

**Validazione degli input.** *Dove avviene e con quali regole.*

**Paginazione.** *Come funziona. Parametri, dimensione di default, formato della risposta.*

**Documentazione e verifica.** *Come userete OpenAPI/Swagger e la collezione Postman.*

---

## Persistenza e modello dei dati

### Diagramma ER

*Inserisci qui il diagramma entità-relazioni con le cardinalità.*

### Identificatori

*Come vengono generati gli ID, e perché. Numeri incrementali, UUID, altro?*

### Tre modelli diversi

| Entità | Nel database | Nel dominio | Esposta dall'API | Dove differiscono e perché |
| --- | --- | --- | --- | --- |
| *es. Voto* | *…* | *…* | *…* | *…* |

### Normalizzazione e letture aggregate

*Come è normalizzato il modello. Dove serve una lettura denormalizzata, per esempio la pagina dei voti per materia o la dashboard del Direttore.*

### Accesso ai dati

*Strategia di accesso ai dati e uso delle query parametrizzate contro la SQL injection.*

---

## Sicurezza e integrazione

### Autenticazione e token

*Come si ottiene il token, cosa contiene, come viaggia il profilo utente.*

### Chi può fare cosa

| Operazione | Direttore | Docente | Studente |
| --- | --- | --- | --- |
| Creare un docente | ✅ | ❌ | ❌ |
| Disattivare un docente | ✅ | ❌ | ❌ |
| Creare, modificare, disattivare uno studente | ✅ | ❌ | ❌ |
| Reinviare le credenziali | ✅ | ❌ | ❌ |
| Creare e comporre le classi, trasferire studenti | ✅ | ❌ | ❌ |
| Vedere la vista d'insieme della scuola | ✅ | ❌ | ❌ |
| Caricare materiale | ✅ | ✅ | ❌ |
| Vedere i voti di uno studente | ✅ | ✅ | ✅ |
| *…* |  |  |  |

*Spiega dove viene fatto rispettare questo controllo. Ricorda che il frontend non basta mai.*

### L'API esterna

*Quale servizio usate, per cosa, e cosa succede quando non risponde.*

### Configurazione e segreti

*Dove vivono connection string e segreti, e come cambiano fra Development e Production.*

---

## Qualità architetturale

### Organizzazione del codice

*Struttura di progetti, moduli e cartelle, con le motivazioni.*

### Dependency inversion e IoC

*Dove li applicate e a cosa servono in ScuolaChill.*

### Testabilità

*Cosa testerete, e come separate database e API esterne per sostituirli nei test.*

### Development e Production

|  | Development | Production |
| --- | --- | --- |
| Database | *…* | *…* |
| Segreti | *…* | *…* |
| Log | *…* | *…* |
| *…* |  |  |

---

## Dimensionamento e costi

| Componente | Servizio | Taglia (CPU, RAM, storage) | Istanze | Costo mensile stimato |
| --- | --- | --- | --- | --- |
| Backend | *…* | *…* | *…* | *…* |
| Database | *…* | *…* | *…* | *…* |
| Storage dei file | *…* | *…* | *…* | *…* |
| *…* |  |  |  |  |
| **Totale** |  |  |  | ***…*** |

**Strategia di scalabilità.** *Verticale o orizzontale? Manuale o automatica?*

**Se la stima si rivela sbagliata.** *Cosa fate se gli utenti sono il doppio? E se sono la metà?*

---

## Piano di deployment

*Come ScuolaChill arriva sul cloud scelto. Come si passa da una versione alla successiva. Come vengono gestite nel tempo le modifiche allo schema del database.*

---

# Terza parte · Tempi e valutazione

## Milestone

| Milestone | Cosa è pronto | Data prevista | Responsabile |
| --- | --- | --- | --- |
| PRD validato | Questo documento | *…* | *tutto il team* |
| *Prima versione in cloud* | *…* | *…* | *…* |
| *Collaudo con il primo anno* | *…* | *…* | *…* |
| *…* |  |  |  |

<aside>
💡

Stima il tempo di ogni fase come se tutto andasse bene. Poi aggiungi un margine. Non va mai tutto bene.

</aside>

## Piano di valutazione

Come capirete che ScuolaChill funziona e come validerete che la vostra soluzione sta avendo un impatto positivo?

| Metrica | Obiettivo | Come la misurate | Quando |
| --- | --- | --- | --- |
| *es. Collaudatori che completano una verifica senza aiuto* | *90%* | *Osservazione durante il collaudo* | *Collaudo* |
| *es. Voti persi* | *0* | *Confronto fra voti inseriti e voti salvati* | *Primo mese* |
|  |  |  |  |

| Metrica | Obiettivo | Come la misurate | Quando |
| --- | --- | --- | --- |
| *es. Collaudatori che completano una verifica senza aiuto* | *90%* | *Osservazione durante il collaudo* | *Collaudo* |
| *es. Voti persi* | *0* | *Confronto fra voti inseriti e voti salvati* | *Primo mese* |
|  |  |  |  |

---

## Acceptance Criteria di questa PRD

- [ ]  Ogni parte rappresentata da questo template ha tutte le sezioni richieste senza saltare nessun punto
- [ ]  Avete deciso tutti i punti che la traccia e gli esempi lasciano aperti.
- [ ]  Ogni requisito non funzionale ha una soglia e una condizione.
- [ ]  Ogni NFR è collegato ad almeno una user story.
- [ ]  Avete inserito i requisiti impliciti emersi da interviste che avete fatto.
- [ ]  Assunzioni, vincoli e dipendenze sono separati e scritti.
- [ ]  I numeri della stima del carico sono coerenti con la scuola immaginata e con il dimensionamento.
- [ ]  Ogni scelta tecnica ha almeno un'alternativa scartata e una motivazione.
- [ ]  La prima parte non contiene scelte tecniche.
- [ ]  Lo storico delle versioni è aggiornato .