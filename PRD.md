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
| **Team** | *nome del team* |
| **Autori** | Daniele Costantini |
| **Versione** | 0 |
| **Data** | 23/09/2026 |
| **Stato** | Bozza |

### Storico delle versioni

| Versione | Data       | Autore             | Cosa è cambiato e perché |
| 0        | 23/09/2026 | Daniele Costantini | Prima stesura            |
| | | | |

> 💡 Il PRD cambierà durante l'anno. Ogni modifica va registrata qui, con la sua ragione. Un PRD che dice una cosa mentre il codice ne fa un'altra è peggio di nessun PRD.

---

# Prima parte · Il cosa

## Scopo e perimetro

### Perché esiste ScuolaChill

**Dal lato business.** *Quale problema risolve, e per chi. Due o tre frasi.*

**Dal lato tecnico.** *Cosa copre il sistema, in grandi linee. Due o tre frasi.*

### Cosa è incluso

- gestione e creazione di classi, docenti e studenti da parte del Direttore
- assegnazione materiale, verifiche e assegnazione voti da parte dei Docenti
- svolgimento verifiche e controllo voti per gli Studenti

### Cosa non è incluso

- *Esempio: ScuolaChill non gestisce le assenze né le comunicazioni con le famiglie*
- *…*

> 💡 La lista di cosa **non** è incluso è la più preziosa del documento. Ogni riga qui ti evita una settimana di discussioni più avanti.

---

## Stakeholder

| Stakeholder       | Cosa fa    | Cosa gli interessa | Come lo coinvolgete |
| Direttore         | *…*        | *…*                | *…*                 |
| Docenti           | *…*        | *…*                | *…*                 |
| Studenti          | *…*        | *…*                | *…*                 |
| Docente del corso | Valida il PRD | *…* | Presentazione e domande |
| Collaudatori del primo anno | Usano ScuolaChill come utenti reali | *…* | *Intervista, collaudo* |
| *Altri?* | | | |

> 💡 Gli stakeholder non sono solo gli utenti. Sono anche chi approva, chi paga, chi manterrà il sistema. Chiediti chi resterebbe deluso se ScuolaChill non funzionasse.

---

## Destinatari e contesto d'uso

### La scuola che avete immaginato

*Descrivi la scuola per cui progettate. Che tipo di istituto è, dove si trova, come si organizza la giornata. Questi dati tornano nella stima del carico, quindi scegli numeri che poi userai davvero.*

| | Valore |
| --- | --- |
| Numero di studenti | *…* |
| Numero di docenti | *…* |
| Numero di classi | 21 |
| Orario scolastico | 8:10 - 13:20 lunedì, mercoledì e venerdì, 8:10 - 16:10 martedì e giovedì|
| Connettività | Wi-Fi scolastico condiviso, rete mobile degli studenti |

### Gli archetipi

Arricchisci gli archetipi della traccia.

| ID | Archetipo | Contesto d'uso | Competenze digitali | Dispositivo principale | Frequenza d'uso |
| --- | --- | --- | --- | --- | --- |
| ARC-001 | Direttore | *…* | *…* | *…* | *…* |
| ARC-002 | Docente | *…* | *…* | *…* | *…* |
| ARC-003 | Studente | *…* | *…* | *…* | *…* |

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
| DIR-01 | Creare account docente | *…* | *…* |
| DIR-02 | Creare account studente | *…* | *…* |
| DIR-03 | Creare classi e comporle | *…* | *…* |
| DIR-04 | Vedere tutto | *…* | *…* |
| DOC-01 | Caricare materiale didattico | *…* | *…* |
| DOC-02 | Creare le proprie verifiche | *…* | *…* |
| DOC-03 | Assegnare i voti | *…* | *…* |
| STU-01 | Consultare il materiale didattico | *…* | *…* |
| STU-02 | Svolgere una verifica | *…* | *…* |
| STU-03 | Consultare i propri voti | *…* | *…* |

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

---

## Requisiti non funzionali

Ogni requisito ha una soglia, una condizione e un modo per verificarlo. Ed è collegato ad almeno una user story.

| ID | Famiglia | Requisito | Soglia e condizione | Come si verifica | Storie collegate |
| --- | --- | --- | --- | --- | --- |
| NFR-01 | Prestazioni | *es. Apertura della verifica nel picco* | *es. meno di 2 s per il 95% delle richieste, 75 utenti nello stesso minuto* | *Test di carico* | *STU-02* |
| NFR-02 | Sicurezza | *…* | *…* | *…* | *…* |
| NFR-03 | Usabilità | *…* | *…* | *…* | *…* |
| NFR-04 | Disponibilità | *…* | *…* | *…* | *…* |
| NFR-05 | Ambientale | *…* | *…* | *…* | *…* |
| NFR-06 | Supporto | *…* | *…* | *…* | *…* |
| NFR-07 | Interazione | *…* | *…* | *…* | *…* |
| NFR-08 | Conformità | *…* | *…* | *…* | *…* |

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
| ASS-01 | *es. La scuola ha 800 studenti e 60 docenti* | *Il dimensionamento va rifatto* |
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