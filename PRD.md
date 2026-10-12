# PRD di ScuolaChill

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
| **Team** |  |
| **Autori** | Daniele Costantini |
| **Versione** | 0.2.2 |
| **Data** | 09/10/2026 |
| **Stato** | Bozza |

### Storico delle versioni

| Versione | Data | Autore | Cosa è cambiato e perché |
| --- | --- | --- | --- |
| 0 | 23/09/2026 | Daniele Costantini | Prima stesura |
| 0.0.1 | 25/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DIR-01 |
| 0.0.2 | 25/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DIR-02 |
| 0.0.3 | 25/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DIR-03 |
| 0.0.4 | 25/09/2026 | Daniele Costantini | Numerazione allineata alla traccia: DIR-03 è "Vedere tutto", DIR-04 è "Creare classi e comporle" |
| 0.0.5 | 25/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DIR-04 |
| 0.0.6 | 25/09/2026 | Daniele Costantini | Storie del Direttore: aggiunti modifica, riattivazione e password dimenticata (DIR-01, DIR-02); user flow e scenari di DIR-01, DIR-02, DIR-04; NFR-04 e NFR-10; permessi del Direttore |
| 0.0.7 | 30/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DOC-01; user flow e scenari di DOC-01 |
| 0.0.8 | 30/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DOC-02, con la proposta sulla modifica di una verifica dopo lo svolgimento (AC-10); user flow e scenari di DOC-02 |
| 0.0.9 | 30/09/2026 | Daniele Costantini | Aggiunti gli AC del team per DOC-03, con la proposta sulla scala dei voti (AC-01); user flow e scenari di DOC-03 |
| 0.1.0 | 02/10/2026 | Daniele Costantini | Aggiunti gli AC del team per STU-01; user flow e scenari di STU-01 |
| 0.1.1 | 02/10/2026 | Daniele Costantini | Aggiunti gli AC del team per STU-02, con la proposta sulla connessione che cade (AC-10, AC-11); user flow e scenari di STU-02 |
| 0.1.2 | 02/10/2026 | Daniele Costantini | Aggiunti gli AC del team per STU-03; user flow e scenari di STU-03 |
| 0.1.3 | 09/10/2026 | Daniele Costantini | Scritto "Perché esiste ScuolaChill", lato business e lato tecnico |
| 0.1.4 | 09/10/2026 | Daniele Costantini | Dispositivi dello studente: iPad a scuola e PC, smartphone solo per consultare fuori da scuola (a scuola resta nell'armadietto). Aggiornati archetipo, scenari e AC di STU-01, STU-02, STU-03; aggiunti NFR-11, ASS-02, ASS-03, VIN-02, VIN-03 |
| 0.1.5 | 09/10/2026 | Daniele Costantini | Numero di studenti allineato a 500 in tutto il documento e nelle storie; NFR-01 tarato su 100 studenti; aggiunte assunzioni ASS-04…ASS-09, vincoli VIN-04…VIN-09 e dipendenze DIP-02…DIP-06; compiti per casa fuori perimetro; scritti utenti concorrenti e profilo di carico |
| 0.1.6 | 09/10/2026 | Daniele Costantini | Compiti per casa dentro il perimetro: nuove storie del team DOC-04 e STU-04 con user flow e scenari; aggiornati panoramica, archetipi, NFR-11, ASS-03, DIP-04, profilo di carico e permessi; aggiunta ASS-10 sullo spazio delle consegne |
| 0.1.7 | 09/10/2026 | Daniele Costantini | I compiti diventano un avviso sul registro: il docente li segna con scadenza e link a Classroom, consegna e correzione restano su Classroom. Così non servono file né spazio in più. Riscritte DOC-04 e STU-04 (ora "Consultare i compiti per casa"); ASS-10 ora riguarda Classroom; aggiornati perimetro, NFR-11, ASS-03, DIP-04, profilo di carico e permessi |
| 0.1.8 | 09/10/2026 | Daniele Costantini | Esclusi in modo esplicito l'account genitore, le note disciplinari e le circolari, che nessuna parte del PRD citava |
| 0.1.9 | 09/10/2026 | Daniele Costantini | Comunicazioni e note disciplinari dentro il perimetro: nuove storie del team DIR-05, DOC-05, DOC-06 e STU-05 con user flow e scenari; aggiornati panoramica, archetipo dello studente, NFR-11, VIN-07, profilo di carico e permessi |
| 0.2.0 | 09/10/2026 | Daniele Costantini | Note disciplinari: confermato che i docenti della classe vedono le note dei colleghi, ma non possono modificarle né annullarle (nuovo DOC-06 AC-06) |
| 0.2.1 | 09/10/2026 | Daniele Costantini | Scelte tecnologiche: completata la tabella con alternative e motivazioni per backend (Node.js), frontend (React) e database (PostgreSQL) |
| 0.2.2 | 12/10/2026 | Daniele Costantini | Tolta la decisione FR-EXT-01 sul fallimento dell'email e tutti i suoi riferimenti (PRD, DIR-01, DIR-02); la decisione sul fallimento del servizio esterno torna aperta |

> 💡 Il PRD cambierà durante l'anno. Ogni modifica va registrata qui, con la sua ragione. Un PRD che dice una cosa mentre il codice ne fa un'altra è peggio di nessun PRD.

---

# Prima parte · Il cosa

## Scopo e perimetro

### Perché esiste ScuolaChill

**Dal lato business.** Oggi materiale, verifiche e voti passano da fotocopie, chiavette, registri cartacei e strumenti diversi per ogni docente: il Direttore non ha una visione d'insieme e gli studenti non sanno dove trovare le cose. ScuolaChill mette la didattica di ogni giorno in un unico posto, così il Direttore governa classi e account senza chiedere a nessuno, i docenti risparmiano tempo nella preparazione e nella correzione delle verifiche, e gli studenti trovano materiale e voti appena sono disponibili.

**Dal lato tecnico.** ScuolaChill è un'applicazione web, usabile dal browser sia da PC sia da iPad, con un accesso personale per ogni utente e tre ruoli (Direttore, Docente, Studente) che vedono e possono fare solo ciò che li riguarda. Il sistema conserva in modo centralizzato account, classi, materiali, compiti, verifiche e voti, corregge da solo le domande chiuse delle verifiche e si appoggia a un servizio email esterno per inviare le credenziali. È pubblicato sul cloud e raggiungibile da internet, anche da casa.

### Cosa è incluso

- Creazione e gestione degli account di docenti e studenti da parte del Direttore
- Creazione delle classi e loro composizione (assegnazione studenti, docenti e materie)
- Caricamento e consultazione del materiale didattico per materia e classe
- Creazione e svolgimento delle verifiche
- Assegnazione e consultazione dei voti, raggruppati per materia
- Compiti per casa sul registro: il docente segna cosa fare, la scadenza e il link al compito su Classroom; lo studente li consulta
- Comunicazioni a senso unico: il Direttore scrive a tutta la scuola, ai docenti, agli studenti o a delle classi; il docente scrive alle sue classi. Nessuna risposta, nessuna email
- Note disciplinari: il docente le segna a uno studente o alla classe, lo studente e il Direttore le vedono. Non incidono su voti e medie
- Vista d'insieme del Direttore su classi, docenti, studenti e andamento dei voti
- Autenticazione e autorizzazione basata sui tre ruoli (Direttore, Docente, Studente)

### Cosa non è incluso

- Gestione delle assenze
- Comunicazioni con le famiglie
- Account per i genitori: i genitori non accedono a ScuolaChill, nemmeno in sola lettura. I ruoli restano tre (Direttore, Docente, Studente)
- Gestione amministrativa/contabile della scuola (rette, pagamenti)
- Orario delle lezioni (timetabling)
- Messaggistica diretta fra utenti (chat)
- Consegna e correzione dei compiti per casa: avvengono su Google Classroom. ScuolaChill mostra solo il link che ti porta su Classroom

> ⚠️ *Questa lista deriva da ciò che la traccia NON menziona fra le funzionalità richieste. Verificatela con il team: se avete in mente di aggiungere qualcosa di più, va spostato sopra, fra "cosa è incluso".*

> 💡 La lista di cosa **non** è incluso è la più preziosa del documento. Ogni riga qui ti evita una settimana di discussioni più avanti.

---

## Stakeholder

| Stakeholder | Cosa fa | Cosa gli interessa | Come lo coinvolgete |
|---|---|---|---|
| Direttore | Dirige la scuola: crea account e classi, supervisiona tutto | Una vista d'insieme affidabile e rapida, senza dover entrare in ogni singola pagina | Intervista, collaudo finale |
| Docenti | Carica materiale, crea verifiche, assegna voti sulle proprie classi/materie | Uno strumento semplice da usare ogni giorno, con dati corretti sui propri studenti | Collaudo |
| Studenti | Consulta materiale, svolge verifiche, controlla i propri voti | Un'app semplice e veloce, comoda sull'iPad in classe e sul PC a casa | Collaudo diretto (ragazzi del primo anno) |
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
| Numero di studenti | 500 |
| Numero di docenti | 18 |
| Numero di classi | 21 |
| Orario scolastico | Lunedì, Mercoledì e Venerdì 8:10 - 13:20 Martedì e Giovedì 8:10 - 16:10 |
| Connettività | Wi-Fi scolastico |

### Gli archetipi

Arricchisci gli archetipi della traccia.

| ID | Archetipo | Contesto d'uso | Competenze digitali | Dispositivo principale | Frequenza d'uso |
| --- | --- | --- | --- | --- | --- |
| ARC-001 | Direttore — dirige la scuola, ha poco tempo, gli serve la visione d'insieme; è l'unico che gestisce anagrafiche e classi | Ufficio, sessioni brevi e mirate | *Ipotesi: medio-basse — serve un'interfaccia semplice, poche azioni per completare un task* | PC/laptop | Quotidiana, ma per sessioni brevi |
| ARC-002 | Docente — insegna una o più materie in una o più classi; assegna compiti, prepara verifiche, carica materiale, valuta gli studenti | Aula, sala professori, casa (preparazione materiale) | *Ipotesi: medie* | PC/laptop, occasionalmente tablet | Quotidiana |
| ARC-003 | Studente — iscritto a una classe; studia sul materiale dei docenti, segue i compiti per casa, svolge le verifiche, tiene d'occhio i propri voti | Aula durante le verifiche, casa per lo studio | *Ipotesi: alte (nativi digitali)* | iPad a scuola (verifiche e consultazione), PC a casa; smartphone fuori da scuola, solo per consultare (tutto tranne le verifiche) | Quotidiana, più volte al giorno |

> ⚠️ *Le colonne "Competenze digitali" e "Frequenza d'uso" sono ipotesi di partenza: vanno confermate (o corrette) con l'intervista ai ragazzi del primo anno prevista più sotto, prima di chiudere la sezione.*

> 💡 I collaudatori veri sono i ragazzi del primo anno. Usano lo smartphone in corridoio o il PC in laboratorio? La risposta cambia l'interfaccia, i requisiti di usabilità e perfino il dimensionamento.

---

## Panoramica e casi d'uso

### ScuolaChill in poche righe

ScuolaChill è il registro della scuola, ma online e tutto in un posto.

Lei crea gli account di docenti e studenti e forma le classi. Poi ognuno fa la sua parte: i docenti caricano il materiale, assegnano i compiti, preparano le verifiche e danno i voti; gli studenti studiano, trovano i compiti da fare, fanno le verifiche sull'iPad e vedono subito i propri voti, materia per materia. Sul registro trovano anche le comunicazioni della scuola e le note disciplinari.

E lei, da una sola pagina, vede come vanno tutte le classi, senza dover chiedere a nessuno.

Assenze, orario, comunicazioni con le famiglie e account per i genitori restano fuori: ci concentriamo sulla didattica di ogni giorno.

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
- *Email non partita:* il servizio email non risponde. L'account viene salvato lo stesso, il Direttore vede un avviso e più tardi reinvia le credenziali dall'elenco docenti.
- *Docente che lascia la scuola:* a fine anno il Direttore disattiva l'account. Il docente non può più accedere, ma le verifiche e i voti che ha dato restano.

**Storia:** DIR-02 Creare account studente

**User flow**

1. Il Direttore accede a ScuolaChill
2. Apre la sezione crea utente e sceglie "Studente"
3. Inserisce nome, cognome, email e, se esiste già, la classe
4. Viene mandata una mail con le credenziali allo studente
5. Al primo accesso lo studente imposta una nuova password e l'account diventa attivo

**Scenario principale.** Durante l'anno arriva un nuovo studente, Luca Galli, che va in 2B. Il Direttore lo crea inserendo i suoi dati e sceglie la classe 2B. Luca riceve l'email, accede dall'iPad, cambia la password e trova subito il materiale e le verifiche della 2B.

**Scenari alternativi.**
- *Classe non ancora creata:* a inizio anno le classi non esistono ancora. Il Direttore crea gli studenti senza classe e li assegna dopo (DIR-04); la vista d'insieme glieli segnala come "studenti senza classe".
- *Email non partita:* come per i docenti, l'account resta salvato e il Direttore reinvia le credenziali.
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

**Storia:** DIR-05 Pubblicare comunicazioni *(storia aggiunta dal team)*

**User flow**

1. Il Direttore accede a ScuolaChill
2. Apre la sezione Comunicazioni e sceglie "Nuova comunicazione"
3. Scrive titolo e testo e sceglie i destinatari: tutta la scuola, i docenti, gli studenti o alcune classi
4. Se serve, allega la circolare o incolla un link e segna la comunicazione "in evidenza"
5. Pubblica: i destinatari la trovano subito, segnata "nuova"

**Scenario principale.** Lunedì il Direttore pubblica a tutta la scuola "Venerdì uscita anticipata alle 11:20 per assemblea", in evidenza fino a venerdì. Docenti e studenti la trovano in cima alla sezione Comunicazioni appena entrano.

**Scenari alternativi.**
- *Solo ai docenti:* il Direttore convoca il collegio docenti scrivendo solo ai docenti; gli studenti non la vedono.
- *Errore nella data:* il Direttore corregge "venerdì" in "giovedì"; tutti vedono la comunicazione segnata come "modificata".
- *Comunicazione scaduta:* dopo venerdì l'avviso esce dall'evidenza e passa fra le comunicazioni vecchie.

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

**Scenario principale.** Il sabato mattina la prof.ssa Neri apre la verifica della 2B chiusa venerdì. Le domande a risposta multipla sono già corrette; lei legge le due aperte di ogni studente e assegna i punti. Per Luca Galli il sistema propone 7, lei lo lascia così e aggiunge "Bene il procedimento, attenzione ai segni". Finito l'ultimo studente pubblica i voti, e Luca li vede dal PC di casa pochi minuti dopo.

**Scenari alternativi.**
- *Interrogazione:* il lunedì la docente interroga due studenti e inserisce subito i due voti orali; gli studenti li vedono in giornata.
- *Studente assente:* uno studente non ha svolto la verifica e risulta "non svolta". La recupera su carta la settimana dopo e la docente gli inserisce il voto a mano.
- *Voto sbagliato:* la docente si accorge di aver dato 5 invece di 6,5. Lo corregge; lo studente vede il voto nuovo e il sistema tiene traccia del cambio.

**Storia:** DOC-04 Assegnare i compiti per casa *(storia aggiunta dal team)*

**User flow**

1. Il Docente accede a ScuolaChill
2. Apre una sua classe e materia e sceglie "Segna compito"
3. Scrive titolo e descrizione, sceglie la scadenza e, se il compito si consegna su Classroom, incolla il link
4. Salva: gli studenti vedono il compito subito

**Scenario principale.** Lunedì la prof.ssa Neri segna per la 2B "Esercizi da 4 a 10 di pagina 132", per giovedì, e incolla il link al compito su Classroom, dove gli studenti caricheranno la foto del quaderno. Seleziona anche la 2C, dove insegna la stessa materia. Gli studenti delle due classi trovano il compito sul registro con la scadenza e il link.

**Scenari alternativi.**
- *Compito sul libro:* per Inglese la docente segna "Leggere pagina 40" senza link: si corregge in classe, non c'è niente da consegnare.
- *Scadenza spostata:* metà classe è in uscita didattica. La docente sposta la scadenza a venerdì e gli studenti vedono il compito segnato come "modificato".
- *Compito valutato:* la docente corregge un tema su Classroom e inserisce il voto su ScuolaChill come prova di tipo "compito" (DOC-03) *(proposta, da confermare)*.

**Storia:** DOC-05 Comunicazioni alle proprie classi *(storia aggiunta dal team)*

**User flow**

1. Il Docente accede a ScuolaChill
2. Apre la sezione Comunicazioni e legge quelle nuove del Direttore
3. Sceglie "Nuova comunicazione", scrive titolo e testo e sceglie una o più delle sue classi
4. Pubblica: gli studenti e i docenti di quelle classi la trovano subito

**Scenario principale.** Martedì la prof.ssa Neri scrive alla 2B e alla 2C: "Giovedì lezione in laboratorio di informatica". Gli studenti la vedono segnata "nuova" la mattina dopo.

**Scenari alternativi.**
- *Classe non sua:* la docente prova a scrivere alla 3A, dove non insegna. La classe non compare fra quelle che può scegliere.
- *Comunicazione di un collega:* il docente di Inglese ha già avvisato la 2B dell'uscita didattica. La prof.ssa Neri lo vede fra le comunicazioni della classe e non lo ripete *(proposta)*.

**Storia:** DOC-06 Assegnare note disciplinari *(storia aggiunta dal team)*

**User flow**

1. Il Docente accede a ScuolaChill
2. Apre una sua classe e sceglie "Nuova nota"
3. Sceglie lo studente (o tutta la classe), la data e scrive il motivo
4. Salva: lo studente e il Direttore vedono la nota

**Scenario principale.** Durante la lezione Luca Galli usa più volte l'iPad per giocare. La prof.ssa Neri segna una nota: "Usa l'iPad per giochi durante la lezione, dopo due richiami". Luca la trova nella sezione Note; il Direttore la vede nell'elenco delle note della scuola.

**Scenari alternativi.**
- *Nota alla classe:* la 2B fa confusione durante il cambio d'ora. La docente segna una nota alla classe e ogni studente la trova fra le sue.
- *Nota sbagliata:* la docente ha scelto lo studente sbagliato. Annulla la nota indicando il motivo e la segna allo studente giusto; la prima resta nello storico come "annullata" *(proposta)*.
- *Curiosità sulle note di un compagno:* uno studente prova ad aprire la nota di Luca. Il sistema rifiuta la richiesta.

**Storia:** STU-01 Consultare il materiale didattico

**User flow**

1. Lo Studente accede a ScuolaChill dall'iPad a scuola o dal PC a casa
2. Apre la sezione Materiale e vede le materie della sua classe
3. Sceglie una materia e scorre i materiali, dal più recente
4. Apre il materiale: il file si scarica o si apre nel browser, il link si apre in una nuova scheda

**Scenario principale.** Lunedì mattina, in classe, Luca Galli apre ScuolaChill dall'iPad. Nella sezione Materiale vede che Matematica ha un materiale nuovo: è il PDF sulle equazioni di secondo grado caricato dalla prof.ssa Neri la sera prima. Lo legge durante la lezione; il pomeriggio lo riapre dal PC di casa per fare gli esercizi.

**Scenari alternativi.**
- *Studente non ancora in una classe:* a inizio anno Luca ha l'account ma il Direttore non l'ha ancora messo in una classe. Nella sezione Materiale trova un messaggio che glielo spiega, non una pagina di errore.
- *Link passato a un compagno di un'altra classe:* Luca copia il link del PDF e lo manda a un amico della 3A. L'amico non riesce ad aprirlo, perché il materiale è solo per la 2B.
- *Materiale eliminato:* la docente elimina un PDF con un errore e ne carica uno corretto. Luca, aprendo il vecchio link salvato, vede che non è più disponibile e trova quello nuovo in cima all'elenco.

**Storia:** STU-02 Svolgere una verifica

**User flow**

1. Lo Studente accede a ScuolaChill
2. Apre la sezione Verifiche e sceglie quella aperta
3. Preme "Inizia": vede le domande e il tempo rimanente
4. Risponde alle domande; ogni risposta si salva da sola
5. Consegna e conferma: la verifica risulta "consegnata"

**Scenario principale.** Venerdì alle 9:00 Luca Galli è in classe con la 2B; lo smartphone è nell'armadietto. Dall'iPad apre la verifica di Matematica sulle equazioni di secondo grado, preme "Inizia" e vede 50 minuti sul contatore. Risponde alle 8 domande a risposta multipla, torna indietro a cambiarne una e scrive le due risposte aperte. Alle 9:42 preme "Consegna": il sistema gli dice che ha risposto a tutto, lui conferma e vede l'ora di consegna. Alle 10:00, alla chiusura, vede le risposte corrette delle domande chiuse; il voto arriverà quando la prof.ssa Neri lo pubblica.

**Scenari alternativi.**
- *Connessione che cade:* a metà verifica il Wi-Fi della scuola si blocca. Luca vede l'avviso "sei offline" e continua a rispondere; dopo due minuti la rete torna e le risposte in sospeso si salvano da sole *(proposta, da confermare)*.
- *iPad che si spegne:* l'iPad di Luca si scarica. La docente gli dà un iPad di riserva o un PC del laboratorio; Luca riapre la verifica e riprende dalle ultime risposte salvate, con il tempo che gli resta.
- *Tempo scaduto:* Luca non fa in tempo a finire l'ultima risposta aperta. Allo scadere dei 50 minuti il sistema consegna da solo quello che ha salvato e la segna come "consegnata automaticamente".

**Storia:** STU-03 Consultare i propri voti

**User flow**

1. Lo Studente accede a ScuolaChill
2. Apre la sezione Voti e vede le sue materie con la media del quadrimestre
3. Sceglie una materia e vede i voti, dal più recente, con data, tipo di prova e commento
4. Se il voto viene da una verifica online, la apre e rivede le sue risposte

**Scenario principale.** Sabato pomeriggio Luca Galli riceve il voto della verifica di Matematica. Apre ScuolaChill dal PC di casa: Matematica ha un voto nuovo, un 7 con il commento "Bene il procedimento, attenzione ai segni". La media della materia passa da 6,25 a 6,50. Luca apre la verifica, guarda la domanda in cui ha sbagliato un segno e la confronta con la risposta corretta.

**Scenari alternativi.**
- *Voto corretto dal docente:* la prof.ssa Neri si accorge di aver sbagliato un voto e lo cambia. Luca vede il voto nuovo, segnato come "modificato", e la media aggiornata.
- *Verifica non svolta:* Luca era assente il giorno della verifica di Inglese. La vede segnata come "non svolta", senza effetto sulla media, finché non arriva il voto del recupero.
- *Curiosità sui voti di un compagno:* Luca prova a cambiare l'ID nell'indirizzo della pagina per vedere i voti di un compagno. Il sistema rifiuta la richiesta.

**Storia:** STU-04 Consultare i compiti per casa *(storia aggiunta dal team)*

**User flow**

1. Lo Studente accede a ScuolaChill, dall'iPad a scuola o dal PC o dal telefono a casa
2. Apre la sezione Compiti e vede quelli da fare, dal più vicino alla scadenza
3. Apre il compito e legge cosa deve fare
4. Se c'è il link, lo apre e consegna su Classroom

**Scenario principale.** Mercoledì pomeriggio Luca Galli apre ScuolaChill dal PC di casa. Nella sezione Compiti vede in evidenza Matematica "per domani": esercizi da 4 a 10 di pagina 132. Li fa sul quaderno, apre il link e carica la foto su Classroom.

**Scenari alternativi.**
- *Compito modificato:* la docente sposta la scadenza a venerdì. Luca vede il compito segnato come "modificato" con la nuova data.
- *Compito senza link:* il compito di Inglese è solo da leggere. Luca lo vede con la scadenza, senza niente da consegnare.
- *Studente non ancora in una classe:* a inizio anno la sezione Compiti mostra un messaggio che spiega che Luca non è ancora in una classe, non un errore.

**Storia:** STU-05 Leggere comunicazioni e note disciplinari *(storia aggiunta dal team)*

**User flow**

1. Lo Studente accede a ScuolaChill
2. Apre la sezione Comunicazioni: in cima trova quelle in evidenza e quelle nuove
3. Apre una comunicazione e, se c'è, l'allegato o il link
4. Nella sezione Note vede le sue note e quelle date alla classe

**Scenario principale.** Lunedì mattina Luca Galli apre ScuolaChill dall'iPad e vede due comunicazioni nuove: l'uscita anticipata di venerdì, in evidenza, e il laboratorio di giovedì della prof.ssa Neri. Le apre e il segno "nuova" sparisce.

**Scenari alternativi.**
- *Nota ricevuta:* Luca trova una nota nella sezione Note, con data, docente e motivo. Non può rispondere.
- *Nota annullata:* la docente annulla una nota data per errore. Luca la vede segnata come "annullata".
- *Studente non ancora in una classe:* a inizio anno Luca vede comunque le comunicazioni a tutta la scuola e a tutti gli studenti.

---

## Requisiti funzionali

### Le user story della traccia

| ID | Storia | AC aggiunti dal team | Note |
| --- | --- | --- | --- |
| DIR-01 | Creare account docente | AC-05 campi obbligatori e formato; AC-06 materie scelte da elenco predefinito; AC-07 cambio password obbligatorio al primo accesso; AC-08 invio email fallito; AC-09 solo il Direttore può creare docenti; AC-10 modifica dei dati; AC-11 riattivazione; AC-12 password dimenticata *(proposta)* (dettaglio in `user-story/DIR-01`) | L'assegnazione del docente alle classi è in DIR-04. Gli account non si eliminano, si disattivano |
| DIR-02 | Creare account studente | AC-01…AC-03 creazione, email unica, campi obbligatori; AC-04 classe facoltativa alla creazione; AC-05/AC-06 stato "in attesa di attivazione" e cambio password al primo accesso; AC-07 invio email fallito; AC-08 disattivazione; AC-09 solo il Direttore può creare studenti; AC-10 creazione da CSV *(da confermare)*; AC-11 modifica dei dati; AC-12 riattivazione; AC-13 password dimenticata *(proposta)* (dettaglio in `user-story/DIR-02`) | Collegata a DIR-04 (composizione e trasferimento fra classi). Stessi stati account di DIR-01 |
| DIR-03 | Vedere tutto | AC-01 riepilogo in prima pagina; AC-02 segnalazioni da sistemare; AC-03…AC-06 elenco e dettaglio di classi, studenti e docenti; AC-07 andamento dei voti per classe, materia e periodo; AC-08 ricerca; AC-09 elenchi paginati e filtrabili; AC-10 sola lettura; AC-11 nessun dato; AC-12 solo il Direttore (dettaglio in `user-story/DIR-03`) | Le medie dipendono dalla decisione sulla scala dei voti (DOC-03). Collegata a NFR-04 (usabilità) e NFR-10 (prestazioni) |
| DIR-04 | Creare classi e comporle | AC-01/AC-02 creazione classe con nome unico per anno scolastico; AC-03/AC-04 aggiunta studenti, uno studente in una sola classe; AC-05…AC-07 materie con un docente abilitato per materia; AC-08 trasferimento *(proposta)*; AC-09 rimozione studente; AC-10 eliminazione solo di classi vuote; AC-11 riepilogo della classe; AC-12 solo il Direttore (dettaglio in `user-story/DIR-04`) | Collegata alla decisione aperta sul trasferimento fra classi: proposta in AC-08, da confermare e poi scrivere come FR |
| DIR-05 | Pubblicare comunicazioni | AC-01 pubblicazione; AC-02 destinatari (scuola, docenti, studenti, classi); AC-03 campi obbligatori; AC-04 allegato PDF o link *(proposta)*; AC-05 in evidenza; AC-06 scadenza *(proposta)*; AC-07 modifica; AC-08 eliminazione; AC-09 letture *(proposta)*; AC-10 elenco di tutte le comunicazioni; AC-11 nessuna risposta; AC-12 solo il Direttore scrive a tutta la scuola (dettaglio in `user-story/direttore/DIR-05`) | Non c'è nella traccia: aggiunta perché le comunicazioni sono dentro il perimetro. Nessuna email: niente costi né dipendenze in più. Collegata a DOC-05 e STU-05 |
| DOC-01 | Caricare materiale didattico | AC-01 caricamento con titolo, classe e materia; AC-02 solo le proprie classi e materie; AC-03 campi obbligatori; AC-04 formati ammessi; AC-05 dimensione massima *(proposta 20 MB)*; AC-06 link esterno *(proposta)*; AC-07 stessa materia in più classi; AC-08 modifica; AC-09 eliminazione; AC-10 elenco paginato; AC-11 caricamento interrotto; AC-12 materiale di chi non insegna più la materia *(proposta)*; AC-13 solo il docente della classe e materia (dettaglio in `user-story/docente/DOC-01`) | Il materiale appartiene alla coppia classe/materia, non al docente. Collegata a DIR-04 e STU-01. Da chiarire se il Direttore può caricare materiale |
| DOC-02 | Creare le proprie verifiche | AC-01 creazione in bozza; AC-02 solo le proprie classi e materie; AC-03/AC-04 tipi di domanda (multipla, vero/falso, aperta) con punteggio e risposta corretta; AC-05 ordine delle domande; AC-06 finestra di svolgimento e durata; AC-07 pubblicazione; AC-08 anteprima; AC-09 modifica prima dell'apertura; AC-10 modifica dopo l'apertura *(proposta)*; AC-11 duplicazione; AC-12 eliminazione; AC-13 elenco paginato; AC-14 correzione automatica delle domande chiuse; AC-15 solo il docente della classe e materia (dettaglio in `user-story/docente/DOC-02`) | Collegata alla decisione aperta sulla modifica dopo lo svolgimento: proposta in AC-10, da confermare e poi scrivere come FR. Il punteggio non è il voto (DOC-03) |
| DOC-03 | Assegnare i voti | AC-01 scala da 1 a 10 con passo 0,5 *(proposta)*; AC-02 correzione della verifica online; AC-03 voto proposto dal punteggio *(proposta)*; AC-04 pubblicazione dei voti di una verifica; AC-05 voto per prove fuori da ScuolaChill (scritto, orale, pratico); AC-06 voti a tutta la classe; AC-07 solo le proprie classi e materie; AC-08 verifica non svolta; AC-09 commento; AC-10 modifica con storico; AC-11 eliminazione con storico; AC-12 voti per quadrimestre *(proposta)*; AC-13 registro della classe; AC-14 solo il docente della classe e materia (dettaglio in `user-story/docente/DOC-03`) | Collegata alla decisione aperta sulla scala dei voti: proposta in AC-01, da confermare e poi scrivere come FR. Le medie di DIR-03 e STU-03 dipendono da qui |
| DOC-04 | Assegnare i compiti per casa | AC-01 compito con titolo, classe, materia e scadenza; AC-02 solo le proprie classi e materie; AC-03 campi obbligatori; AC-04 link al compito su Classroom; AC-05 nessuna consegna su ScuolaChill; AC-06 stesso compito in più classi; AC-07 modifica; AC-08 eliminazione; AC-09 elenco paginato; AC-10 voto del compito *(proposta)*; AC-11 compiti di chi non insegna più la materia; AC-12 solo il docente della classe e materia (dettaglio in `user-story/docente/DOC-04`) | Non c'è nella traccia: aggiunta perché i compiti sono dentro il perimetro. Il registro avvisa, la consegna avviene su Classroom (ASS-10). Collegata a DOC-03 e STU-04 |
| DOC-05 | Comunicazioni alle proprie classi | AC-01 pubblicazione alle proprie classi; AC-02 solo le proprie classi; AC-03 campi obbligatori; AC-04 link; AC-05 modifica ed eliminazione; AC-06 comunicazioni ricevute; AC-07 comunicazioni inviate; AC-08 nessuna risposta; AC-09 solo i docenti della classe (dettaglio in `user-story/docente/DOC-05`) | Non c'è nella traccia. Stesse regole di DIR-05. Collegata a STU-05 |
| DOC-06 | Assegnare note disciplinari | AC-01 nota a uno studente; AC-02 solo gli studenti delle proprie classi; AC-03 campi obbligatori; AC-04 nota alla classe; AC-05 chi vede la nota; AC-06 i colleghi della classe vedono ma non modificano; AC-07 modifica con storico; AC-08 annullamento *(proposta)*; AC-09 il Direttore vede e annulla; AC-10 note della classe; AC-11 nessun effetto su voti e medie; AC-12 solo i docenti scrivono note (dettaglio in `user-story/docente/DOC-06`) | Non c'è nella traccia: aggiunta perché le note sono dentro il perimetro. Dati delicati di minori (VIN-07). Collegata a DOC-03 (storico) e STU-05 |
| STU-01 | Consultare il materiale didattico | AC-01 materiale diviso per materia; AC-02 elenco paginato dal più recente; AC-03 apertura di un file; AC-04 apertura di un link; AC-05 solo il materiale della propria classe; AC-06 materiale nuovo *(proposta)*; AC-07 ricerca; AC-08 usabile da iPad, PC e smartphone; AC-09 nessun materiale; AC-10 studente senza classe; AC-11 materiale modificato o eliminato; AC-12 file non disponibile; AC-13 cambio di classe *(proposta)*; AC-14 sola lettura (dettaglio in `user-story/studente/STU-01`) | Collegata a DOC-01 (caricamento) e DIR-04 (trasferimento fra classi). Collegata a NFR-11 (dispositivi) |
| STU-02 | Svolgere una verifica | AC-01 elenco delle verifiche; AC-02 apertura solo nella finestra; AC-03 inizio e tempo disponibile; AC-04 tempo rimanente calcolato dal server; AC-05 risposte e navigazione fra le domande; AC-06 salvataggio automatico; AC-07 consegna con conferma; AC-08 consegna automatica allo scadere; AC-09 un solo tentativo; AC-10 connessione che cade *(proposta)*; AC-11 tempo scaduto offline *(proposta)*; AC-12 risposte corrette mai visibili durante la verifica; AC-13 dopo la consegna *(proposta)*; AC-14 verifica non svolta; AC-15 verifica modificata dal docente durante lo svolgimento; AC-16 usabile da iPad e PC; AC-17 solo le verifiche della propria classe (dettaglio in `user-story/studente/STU-02`) | Collegata alla decisione aperta sulla connessione che cade: proposta in AC-10 e AC-11, da confermare e poi scrivere come FR. Collegata a DOC-02 (AC-10, AC-14, AC-15), NFR-01 e NFR-11 |
| STU-03 | Consultare i propri voti | AC-01 voti raggruppati per materia; AC-02 dettaglio di una materia; AC-03 solo i voti pubblicati; AC-04 media della materia; AC-05 voti per quadrimestre; AC-06 voto insufficiente in evidenza; AC-07 voto nuovo *(proposta)*; AC-08 voto di una verifica online; AC-09 verifica non svolta; AC-10 voto modificato o eliminato; AC-11 riepilogo generale *(proposta)*; AC-12 nessun voto; AC-13 cambio di classe; AC-14 usabile da iPad, PC e smartphone; AC-15 solo i propri voti (dettaglio in `user-story/studente/STU-03`) | Voti e medie dipendono dalla decisione sulla scala dei voti (DOC-03 AC-01). Stesse regole di calcolo delle medie di DIR-03. Collegata a NFR-11 |
| STU-04 | Consultare i compiti per casa  | AC-01 elenco dalla scadenza più vicina; AC-02 dettaglio; AC-03 apertura del link; AC-04 scadenza vicina in evidenza; AC-05 compiti scaduti; AC-06 compito nuovo *(proposta)*; AC-07 compito modificato o eliminato; AC-08 nessun compito; AC-09 studente senza classe; AC-10 usabile da iPad, PC e smartphone; AC-11 solo i compiti della propria classe; AC-12 sola lettura (dettaglio in `user-story/studente/STU-04`) | Non c'è nella traccia: aggiunta perché i compiti sono dentro il perimetro. Collegata a DOC-04 e NFR-11 |
| STU-05 | Leggere comunicazioni e note disciplinari | AC-01 elenco delle comunicazioni; AC-02 dettaglio; AC-03 comunicazione nuova; AC-04 comunicazione modificata o eliminata; AC-05 le proprie note; AC-06 nota modificata o annullata; AC-07 solo le proprie note; AC-08 nessuna comunicazione o nota; AC-09 studente senza classe; AC-10 cambio di classe *(proposta)*; AC-11 usabile da iPad, PC e smartphone; AC-12 sola lettura (dettaglio in `user-story/studente/STU-05`) | Non c'è nella traccia. Collegata a DIR-05, DOC-05, DOC-06 e NFR-11 |

> 💡 Gli AC completi (già scritti nella traccia) restano nel documento della traccia stessa come riferimento; qui riportate solo quelli che il team **aggiunge**.

> 💡 Gli acceptance criteria della traccia sono il minimo. Puoi aggiungerne, non toglierne. Scrivi quelli nuovi nello stesso formato *Dato che / Quando / Allora*.

### Le decisioni lasciate aperte dalla traccia

La traccia lascia alcune scelte a te. Ognuna diventa un requisito con il suo ID. Usa questo formato.

> **FR-[AREA]-[NN] · [Titolo]** (collegato a *ID della storia*)
> *Cosa avete deciso, in modo verificabile. Motivazione: perché avete scelto così.*

I punti che devi decidere almeno sono questi.

- [x] La scala dei voti (DOC-03). Da quanto a quanto, con quale passo, se ammette segni come "+" e "−".
- [x] Il trasferimento di uno studente fra classi (DIR-04). Si può fare? Cosa succede ai voti?
- [ ] La modifica di una verifica dopo lo svolgimento (DOC-02).
- [ ] La connessione che cade durante una verifica (STU-02).
- [ ] Il fallimento del servizio esterno (per esempio l'email delle credenziali).
- [ ] *Altre decisioni che il team ha scoperto*

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
| NFR-01 | Prestazioni | Apertura della verifica nel picco delle 9:00 | Meno di 2 s per il 95% delle richieste, con 100 studenti che la aprono nello stesso minuto | Test di carico | STU-02 |
| NFR-02 | Sicurezza | Tutto il traffico fra frontend e backend viaggia su HTTPS | Nessuna chiamata in chiaro, certificato valido | Ispezione del traffico / certificato | Tutte |
| NFR-03 | Sicurezza | Il controllo dei ruoli (Direttore/Docente/Studente) è applicato lato backend su ogni endpoint | Ogni chiamata API verifica il ruolo indipendentemente dal frontend | Test con Postman usando token di ruoli diversi | Tutte |
| NFR-04 | Usabilità | Dalla vista d'insieme il Direttore raggiunge la pagina che risolve una segnalazione (studente senza classe, materia senza docente, email non partita) con un solo click | 1 click da ogni segnalazione, senza passare da menu intermedi | Prova con un collaudatore nel ruolo di Direttore | DIR-03, DIR-04 |
| NFR-05 | Disponibilità | Il sistema è deployato sull'infrastruttura cloud scelta e raggiungibile pubblicamente | Uptime minimo durante il periodo di collaudo (da definire, es. 99%) | Monitoraggio / test di raggiungibilità | Tutte |
| NFR-06 | Ambientale | *…da definire — es. dimensionamento minimo per contenere i costi cloud entro il budget* | *…* | *…* | *…* |
| NFR-07 | Supporto | L'applicazione gira in due configurazioni separate, Development e Production, senza segreti nel codice sorgente | Segreti gestiti tramite variabili d'ambiente / secret manager | Revisione della configurazione e del repository | *Trasversale* |
| NFR-08 | Interazione | Le API principali sono documentate con OpenAPI/Swagger e verificate con una collezione Postman | Copertura di tutte le route CRUD principali | Revisione Swagger + esecuzione della collezione Postman | Tutte |
| NFR-09 | Conformità | Gli elenchi (studenti, materiali, voti) sono paginati e le risposte di errore hanno un formato uniforme con codici HTTP coerenti | Paginazione su ogni collezione, schema di errore unico su tutta l'API | Test automatici sulle risposte | DIR-03, STU-01, STU-03 |
| NFR-10 | Prestazioni | La vista d'insieme del Direttore (riepilogo, segnalazioni, medie) si apre rapidamente anche con tutta la scuola caricata | Meno di 2 s per il 95% delle aperture, con 500 studenti, 21 classi e un quadrimestre di voti — *da tarare sulla stima di carico* | Test di carico su dati di prova della dimensione della scuola | DIR-03 |
| NFR-11 | Usabilità | Le pagine dello studente sono pensate per l'iPad (touch, orientamento verticale e orizzontale) e per il PC. Materiale, voti, compiti, comunicazioni e note si consultano anche da smartphone; le verifiche non sono progettate per lo smartphone | Su iPad e PC ogni pagina dello studente si usa senza zoomare né scorrere in orizzontale, e la verifica si svolge per intero con la tastiera a schermo dell'iPad. Da smartphone (360 px di larghezza) materiale, voti, compiti, comunicazioni e note restano leggibili | Prova dei collaudatori del primo anno su iPad, PC e smartphone, con i browser di VIN-03 | STU-01, STU-02, STU-03, STU-04, STU-05 |

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
| ASS-01 | La scuola ha 500 studenti e 18 docenti | Il dimensionamento va rifatto |
| ASS-02 | A scuola ogni studente ha un iPad a disposizione, almeno durante le verifiche | Le verifiche vanno fatte a turni sui PC del laboratorio e il picco delle 9:00 cambia |
| ASS-03 | Da casa lo studente consulta materiale, voti e compiti con un PC o uno smartphone collegato a internet | Lo studente senza connessione a casa può consultare materiale, voti e compiti solo dall'iPad a scuola: va previsto il tempo per farlo durante la giornata |
| ASS-04 | Ogni docente e ogni studente ha un indirizzo email personale valido, a cui arrivano le credenziali | Il Direttore deve consegnare le credenziali a mano; DIR-01 e DIR-02 vanno ripensati |
| ASS-05 | Il Wi-Fi della scuola regge 100 studenti in verifica nello stesso momento | La connessione che cade (STU-02 AC-10) diventa la regola, non l'eccezione; le verifiche vanno fatte a turni |
| ASS-06 | C'è un solo Direttore, l'unico che gestisce account e classi | Servono più account Direttore e regole per le modifiche fatte da due persone insieme |
| ASS-07 | L'anno scolastico è diviso in due quadrimestri, con date decise dalla scuola | Voti e medie per periodo (DOC-03 AC-12, STU-03 AC-05) vanno ripensati |
| ASS-08 | Ogni docente carica circa 3 materiali a settimana, in media di 2 MB: con 18 docenti e 33 settimane sono circa 1.800 file e 4 GB l'anno | Lo spazio per i file va ridimensionato |
| ASS-09 | I dati nascono in ScuolaChill: non si importa nulla da un registro esistente, a parte l'elenco degli studenti da CSV (DIR-02 AC-10) | Serve una migrazione dei dati, oggi fuori dal perimetro |
| ASS-10 | La scuola usa già Google Classroom per la consegna e la correzione dei compiti, e ogni studente ha un account | Consegna e correzione dei compiti non hanno un posto: vanno fatte in classe, oppure dentro ScuolaChill, con spazio per i file e costi in più |
| | | |

### Vincoli

I limiti che non potete cambiare.

| ID | Vincolo | Da dove viene |
| --- | --- | --- |
| VIN-01 | Il budget cloud è quello dei crediti studente messi a disposizione per il progetto *(importo da inserire)* | Traccia del progetto |
| VIN-02 | A scuola gli studenti non usano lo smartphone, che resta nell'armadietto: si usano solo l'iPad e i PC del laboratorio | Regolamento della scuola |
| VIN-03 | ScuolaChill deve funzionare su Safari per iPadOS e sui principali browser per PC (Chrome, Edge, Firefox, Safari) | Dispositivi in uso nella scuola (VIN-02) |
| VIN-04 | Il progetto va consegnato e collaudato entro le date della traccia (vedi Milestone) | Traccia del progetto |
| VIN-05 | Il lavoro è svolto dal team Regeestro, con le persone e le competenze che ha *(da completare: componenti e ore disponibili)* | Organizzazione del corso |
| VIN-06 | Sono obbligatori: HTTPS, elenchi paginati, errori uniformi, documentazione delle API, ambienti Development e Production separati (NFR-02, NFR-07, NFR-08, NFR-09) | Traccia del progetto |
| VIN-07 | ScuolaChill tratta dati personali di minori (anagrafica, voti e note disciplinari): va rispettato il GDPR, ognuno vede solo i dati che gli servono e i dati non escono dall'uso scolastico | Normativa sulla protezione dei dati (GDPR) |
| VIN-08 | ScuolaChill è un'applicazione web: non c'è un'app da installare | Traccia del progetto |
| VIN-09 | L'interfaccia è solo in italiano | Scuola italiana, utenti italiani |
| | | |

### Dipendenze

Le cose esterne senza cui non potete andare avanti.

| ID | Dipendenza | Serve entro | Chi se ne occupa |
| --- | --- | --- | --- |
| DIP-01 | Account attivo sul servizio email per l'invio delle credenziali (DIR-01, DIR-02) | Prima del collaudo | *nome* |
| DIP-02 | Account attivo sul provider cloud, con i crediti studente (VIN-01) | Prima del primo deploy | *nome* |
| DIP-03 | Un dominio e un certificato valido per l'HTTPS (NFR-02) | Prima del collaudo | *nome* |
| DIP-04 | Uno spazio di archiviazione per i file del materiale didattico (DOC-01, STU-01) | Prima di sviluppare DOC-01 | *nome* |
| DIP-05 | Disponibilità dei ragazzi del primo anno per l'intervista sui requisiti impliciti e per il collaudo | Intervista prima di chiudere gli NFR; collaudo a fine progetto | *nome* |
| DIP-06 | Conferma del docente del corso sulle proposte ancora aperte (trasferimento fra classi, creazione da CSV, modifica della verifica, connessione che cade) | Prima di scrivere i relativi FR | *nome* |
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
| Uso normale durante la giornata | 200 | Durante le lezioni circa un terzo delle classi (7 su 21, circa 170 studenti) usa ScuolaChill sull'iPad, più i docenti e chi studia da casa |
| Picco delle 9:00 (verifiche) | 100 | 4 classi in verifica alla stessa ora × 24 studenti ≈ 100. Sono meno utenti dell'uso normale, ma fanno tutti la stessa cosa nello stesso minuto |
| Fine quadrimestre (voti) | 400 | La mattina o pomeriggio circa l'80% accede a ScuolaChill per la pagella |

### Profilo di carico

| Operazione | Frequente? | Pesante? | Critica? | Note |
| --- | --- | --- | --- | --- |
| Login | Sì: fra le 8:10 e le 8:20 entra tutta la scuola (500 in 10 minuti, circa 1 al secondo) | Sì: il controllo della password consuma CPU | Media: senza login non si fa nulla | Una sessione lunga sull'iPad riduce i login ripetuti |
| Apertura verifica | Sì: 100 studenti nello stesso minuto | No | Alta: la verifica inizia per tutti alla stessa ora | NFR-01 |
| Salvataggio di una risposta | La più frequente: 100 studenti, una risposta ogni 3-5 secondi, circa 20-35 al secondo | No | Altissima: una risposta persa è un voto sbagliato | STU-02 AC-06 |
| Consegna verifica | Picco alla chiusura: le consegne automatiche arrivano tutte nello stesso istante | Sì: parte la correzione automatica delle domande chiuse | Alta: nessuna consegna va persa | La correzione può avvenire subito dopo, senza far aspettare lo studente |
| Consultazione e download del materiale | Sì, tutto il giorno | Il file sì, fino a 20 MB | Media | I file non devono pesare sul resto del sistema |
| Caricamento materiale | No, pochi al giorno | Sì, fino a 20 MB | Bassa | DOC-01 AC-05, ASS-08 |
| Consultazione dei compiti | Sì, soprattutto il pomeriggio e la sera da casa | No: solo testo e link | Bassa | STU-04; nessun file, la consegna è su Classroom |
| Lettura delle comunicazioni | Sì: all'inizio della giornata quasi tutti la aprono (fino a 500 in 10 minuti, insieme al login) | No: solo testo, allegati rari | Bassa | STU-05, DIR-05 |
| Note disciplinari | No: poche a settimana | No | Media: dati delicati, vanno protetti più che velocizzati | DOC-06, VIN-07 |
| Consultazione dei voti | Sì, a fine quadrimestre (400 utenti) | No | Media | STU-03 |
| Pubblicazione dei voti | No | Poco | Alta: i voti di una verifica escono tutti o nessuno | Scatena il picco di consultazioni |
| Dashboard del Direttore | No: un solo utente, poche volte al giorno | Sì: medie su tutta la scuola | Bassa | NFR-10; i numeri possono essere aggiornati a intervalli, non a ogni apertura |
| Creazione degli account (anche da CSV) | No: soprattutto a inizio anno | Sì: fino a 500 account e 500 email insieme | Bassa | Le email partono una alla volta, senza bloccare il Direttore |

In sintesi: il carico è piccolo (al massimo qualche decina di richieste al secondo), ma concentrato in pochi momenti. Il punto delicato non è la velocità, è non perdere risposte e consegne durante le verifiche.

<aside>
💡

I numeri di qui devono essere coerenti con la scuola che avete immaginato e con i requisiti non funzionali. Se dichiarate 800 studenti, non potete dimensionare per 20 utenti senza spiegare perché.

</aside>

---

## Scelte tecnologiche

| Area | Scelta | Alternativa considerata | Perché avete scelto così |
| --- | --- | --- | --- |
| Backend | Node.js con Express | Next.js anche per le API (un solo progetto) | API REST separate, facili da documentare e provare (NFR-08), con il controllo dei ruoli in un posto solo (NFR-03) |
| Frontend | React con Next.js | React con Vite | Routing pronto per le tre aree; con lo static export non serve un server in più |
| Database | PostgreSQL | MongoDB | I dati sono relazionali: vincoli (uno studente in una sola classe), transazioni (pubblicazione dei voti) e medie (DIR-03) si fanno bene in SQL |
| Provider cloud | Microsoft Azure | AWS | Crediti Azure for Students senza carta di credito (VIN-01) e servizi gestiti per Node.js e PostgreSQL |
| Servizi cloud |  |  |  |
| Regione | Italy North (Milano) | West Europe (Paesi Bassi) | Dati di minori in Italia, quindi in UE per il GDPR (VIN-07), e tempi di risposta più bassi |
| Servizio esterno |  |  |  |

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
| Segnare, modificare ed eliminare i compiti | ❌ | ✅ | ❌ |
| Vedere i compiti di una classe (lo studente solo della propria) | ✅ | ✅ | ✅ |
| Pubblicare comunicazioni a tutta la scuola, ai docenti o agli studenti | ✅ | ❌ | ❌ |
| Pubblicare comunicazioni alle proprie classi | ✅ | ✅ | ❌ |
| Leggere le comunicazioni ricevute | ✅ | ✅ | ✅ |
| Segnare una nota disciplinare | ❌ | ✅ | ❌ |
| Modificare una nota disciplinare | ❌ | ✅ (solo le proprie) | ❌ |
| Annullare una nota disciplinare | ✅ | ✅ (solo le proprie, non quelle dei colleghi) | ❌ |
| Vedere le note disciplinari | ✅ (tutte) | ✅ (tutte quelle delle proprie classi, anche dei colleghi) | ✅ (solo le proprie) |
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