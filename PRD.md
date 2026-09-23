# PRD di ScuolaChill · Team [nome del team]

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
| **Versione** | 0 |
| **Data** | 23/09/2026 |
| **Stato** | Bozza |

### Storico delle versioni

| Versione | Data | Autore | Cosa è cambiato e perché |
| --- | --- | --- | --- |
| 0 | 23/09/2026 | Daniele Costantini | Prima stesura |
| | | | |

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

*Racconta ScuolaChill come lo spiegheresti al Direttore in un minuto. Niente termini tecnici.*

### User flow e scenari

Per ogni ruolo, scegli **almeno tre** storie principali e descrivi il percorso completo.

**Storia:** *es. STU-02 · Svolgere una verifica*

**User flow**

1. *Lo studente accede a ScuolaChill*
2. *Apre la sezione Verifiche*
3. *…*

**Scenario principale.** *Racconta il caso in cui tutto va bene, con un personaggio e una situazione concreta.*

**Scenari alternativi.** *Cosa succede quando qualcosa va storto? Connessione che cade, scadenza superata, doppia scheda aperta…*

*Ripeti il blocco per le storie principali di Direttore e Docente.*

---

## Requisiti funzionali

### Le user story della traccia

| ID | Storia | AC aggiunti dal team | Note |
| --- | --- | --- | --- |
| DIR-01 | Creare account docente | *…da aggiungere, se servono, oltre ai 3 AC della traccia* | *…* |
| DIR-02 | Creare account studente | *…* | *…* |
| DIR-03 | Creare classi e comporle | *…* | *Collegata alla decisione aperta sul trasferimento fra classi* |
| DIR-04 | Vedere tutto | *…* | *…* |
| DOC-01 | Caricare materiale didattico | *…* | *…* |
| DOC-02 | Creare le proprie verifiche | *…* | *Collegata alla decisione aperta sulla modifica dopo lo svolgimento* |
| DOC-03 | Assegnare i voti | *…* | *Collegata alla decisione aperta sulla scala dei voti* |
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
- [ ] Il trasferimento di uno studente fra classi (DIR-03). Si può fare? Cosa succede ai voti?
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
| NFR-01 | Prestazioni | *es. Apertura della verifica nel picco* | *es. meno di 2 s per il 95% delle richieste, 75 utenti nello stesso minuto — da tarare sulla vostra stima di carico* | *Test di carico* | STU-02 |
| NFR-02 | Sicurezza | Tutto il traffico fra frontend e backend viaggia su HTTPS | Nessuna chiamata in chiaro, certificato valido | Ispezione del traffico / certificato | Tutte |
| NFR-03 | Sicurezza | Il controllo dei ruoli (Direttore/Docente/Studente) è applicato lato backend su ogni endpoint | Ogni chiamata API verifica il ruolo indipendentemente dal frontend | Test con Postman usando token di ruoli diversi | Tutte |
| NFR-04 | Usabilità | *…da definire — es. numero massimo di click per completare STU-02* | *…* | *…* | *…* |
| NFR-05 | Disponibilità | Il sistema è deployato sull'infrastruttura cloud scelta e raggiungibile pubblicamente | Uptime minimo durante il periodo di collaudo (da definire, es. 99%) | Monitoraggio / test di raggiungibilità | Tutte |
| NFR-06 | Ambientale | *…da definire — es. dimensionamento minimo per contenere i costi cloud entro il budget* | *…* | *…* | *…* |
| NFR-07 | Supporto | L'applicazione gira in due configurazioni separate, Development e Production, senza segreti nel codice sorgente | Segreti gestiti tramite variabili d'ambiente / secret manager | Revisione della configurazione e del repository | *Trasversale* |
| NFR-08 | Interazione | Le API principali sono documentate con OpenAPI/Swagger e verificate con una collezione Postman | Copertura di tutte le route CRUD principali | Revisione Swagger + esecuzione della collezione Postman | Tutte |
| NFR-09 | Conformità | Gli elenchi (studenti, materiali, voti) sono paginati e le risposte di errore hanno un formato uniforme con codici HTTP coerenti | Paginazione su ogni collezione, schema di errore unico su tutta l'API | Test automatici sulle risposte | DIR-04, STU-01, STU-03 |

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
| ASS-01 | La scuola ha 484 studenti e 18 docenti | *Il dimensionamento va rifatto* |
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
| DIP-01 | *es. Account attivo sul servizio email* | *Prima del collaudo* | *nome* |
| | | | |