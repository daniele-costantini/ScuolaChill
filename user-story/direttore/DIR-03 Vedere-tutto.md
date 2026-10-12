# DIR-03 · Vedere tutto

**Ruolo:** Direttore (ARC-001)

**Storia**

Come Direttore, voglio avere una vista d'insieme su classi, docenti, studenti e andamento dei voti, per tenere sotto controllo la scuola senza dover entrare in ogni singola pagina o chiedere ai docenti.

---

## Acceptance criteria della traccia

> 💡 Riportare qui gli AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Riepilogo in prima pagina**
Dato che sono autenticato come Direttore, quando apro ScuolaChill, allora vedo subito un riepilogo con il numero di classi, di docenti attivi, di studenti attivi e di account ancora "in attesa di attivazione".

**AC-02 · Segnalazioni da sistemare**
Dato che ci sono situazioni che richiedono un mio intervento, quando apro la vista d'insieme, allora vedo in evidenza: studenti senza classe, classi con materie senza docente, docenti disattivati ancora assegnati a una classe, email di attivazione non partite e link di attivazione scaduti senza che l'account sia stato attivato. Da ogni segnalazione posso andare direttamente alla pagina per risolverla.

**AC-03 · Elenco classi**
Dato che sono nella vista d'insieme, quando apro l'elenco classi, allora per ogni classe vedo il nome, il numero di studenti, le materie con il rispettivo docente e la media dei voti della classe.

**AC-04 · Dettaglio classe**
Dato che seleziono una classe, quando si apre il dettaglio, allora vedo l'elenco dei suoi studenti e la media dei voti per ogni materia.

**AC-05 · Dettaglio studente**
Dato che seleziono uno studente, quando si apre il dettaglio, allora vedo la sua classe, lo stato dell'account e tutti i suoi voti raggruppati per materia, con la media per materia.

**AC-06 · Dettaglio docente**
Dato che seleziono un docente, quando si apre il dettaglio, allora vedo le materie che insegna, le classi a cui è assegnato, le verifiche che ha creato e il numero di voti assegnati.

**AC-07 · Andamento dei voti**
Dato che voglio capire come sta andando la scuola, quando apro la sezione andamento, allora vedo la media dei voti per classe e per materia, e posso restringerla a un periodo (es. quadrimestre).

**AC-08 · Ricerca**
Dato che cerco uno studente o un docente, quando scrivo almeno tre lettere del nome o del cognome, allora il sistema mi mostra i risultati corrispondenti da cui posso aprire il dettaglio.

**AC-09 · Elenchi paginati e filtrabili**
Dato che gli elenchi di studenti (500) e docenti sono lunghi, quando li consulto, allora sono divisi in pagine e posso filtrarli per classe e per stato dell'account (attivo, in attesa di attivazione, disattivato); di default vedo solo gli account attivi.

**AC-10 · Sola lettura**
Dato che sono nella vista d'insieme, quando consulto voti e verifiche, allora li posso solo vedere: voti e verifiche li modificano esclusivamente i docenti che li hanno creati.

**AC-11 · Nessun dato**
Dato che la scuola è appena stata configurata e non ci sono ancora voti, quando apro l'andamento, allora vedo un messaggio chiaro ("Nessun voto ancora assegnato") invece di medie vuote o a zero.

**AC-12 · Solo il Direttore vede tutto**
Dato che sono autenticato come Docente o Studente, quando provo ad accedere alla vista d'insieme (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

---

## Regole e dati

| Indicatore | Come si calcola |
| --- | --- |
| Media voti di uno studente per materia | Media dei voti dello studente in quella materia nel periodo scelto |
| Media voti di una classe per materia | Media dei voti di tutti gli studenti della classe in quella materia |
| Media voti di una classe | Media delle medie per materia della classe |
| Studenti / docenti attivi | Account nello stato "attivo" |

- Le medie dipendono dalla **scala dei voti** (decisione aperta di DOC-03): se si ammettono "+" e "−", va deciso quanto valgono (es. 6+ = 6,25).
- Gli account disattivati non entrano nei conteggi degli "attivi", ma i loro voti restano nelle medie storiche.

## Fuori perimetro di questa storia

- Creare o modificare account → **DIR-01**, **DIR-02**
- Creare o comporre classi → **DIR-04** (la vista porta lì tramite le segnalazioni, AC-02)
- Modificare voti o verifiche (AC-10)
- Esportare report (PDF/Excel) *(da decidere: servirebbe al Direttore?)*
- Assenze e comunicazioni con le famiglie (fuori perimetro del PRD)

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Decisione aperta | Scala dei voti (DOC-03) | Serve per calcolare le medie (AC-05, AC-07) |
| Decisione aperta | Trasferimento fra classi (DIR-04) | Da decidere in quale classe contano i voti di uno studente trasferito |
| NFR | NFR-03 | Controllo ruolo lato backend (AC-12) |
| NFR | NFR-09 | Elenchi paginati (AC-09) |
| NFR | NFR-10 · Prestazioni | La vista d'insieme si apre in meno di 2 s anche con 500 studenti (il Direttore ha poco tempo, ARC-001) |
| NFR | NFR-04 · Usabilità | Da una segnalazione alla pagina che la risolve con un solo click (AC-02) |
| Storia | DIR-01, DIR-02 | Stati degli account e reinvio del link di attivazione |
| Storia | DIR-04 | Classi, materie e docenti assegnati |
| Storia | DOC-02, DOC-03 | Verifiche e voti che la vista mostra |

## Domande aperte per il team

1. Il Direttore deve poter correggere un voto sbagliato, o resta solo lettura come in AC-10? *(proposta: solo lettura, chiede al docente di correggerlo)*
2. Come è diviso l'anno: quadrimestri, trimestri? Serve per il filtro per periodo in AC-07.
3. Oltre alle medie, al Direttore serve vedere gli studenti in difficoltà (es. media sotto il 6 in una materia)?
4. Serve esportare i dati (es. voti di una classe in Excel)?
