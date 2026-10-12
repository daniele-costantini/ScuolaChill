# DOC-07 · Fare l'appello

**Ruolo:** Docente (ARC-002)

**Storia**

Come Docente, voglio segnare chi è assente nella mia ora di lezione e registrare le giustificazioni che gli studenti mi portano, perché resti traccia delle presenze di ogni studente, ora per ora e giorno per giorno.

---

## Acceptance criteria della traccia

> 💡 Storia aggiunta dal team: la traccia non la prevede, quindi non ci sono AC della traccia da riportare.

## AC aggiunti dal team

**AC-01 · Il mio orario**
Dato che sono autenticato come Docente, quando apro ScuolaChill, allora vedo il mio orario della settimana (DIR-06) e, in evidenza, l'ora che sto facendo adesso, con la classe e la materia.

**AC-02 · Appello della mia ora**
Dato che sono nella mia ora di lezione, quando apro l'appello, allora vedo l'elenco degli studenti della classe, tutti segnati "presente"; segno chi è assente e salvo.

**AC-03 · Appello precompilato dall'ora prima**
Dato che nell'ora precedente un docente ha già fatto l'appello, quando apro il mio, allora gli studenti assenti nell'ora prima sono già segnati assenti. Confermo, oppure cambio chi è entrato o uscito.

**AC-04 · Solo le mie ore**
Dato che sto facendo l'appello, quando scelgo classe e ora, allora posso farlo solo per le ore in cui l'orario mi assegna a quella classe (DIR-06).

**AC-05 · Appello fatto dopo** *(proposta, da confermare)*
Dato che ho dimenticato l'appello, quando lo apro più tardi nella stessa giornata, allora posso ancora compilarlo. Dal giorno dopo posso solo correggerlo (AC-06).

**AC-06 · Correzione con storico**
Dato che ho segnato un'assenza sbagliata, quando la correggo, allora lo studente vede la versione nuova, segnata come "modificata", e il sistema tiene traccia di chi ha cambiato cosa e quando (come per i voti, DOC-03 AC-10). Posso correggere fino a 7 giorni dopo *(proposta)*.

**AC-07 · Riepilogo della giornata**
Dato che gli appelli di una giornata sono fatti, quando guardo una classe, allora per ogni studente vedo lo stato della giornata, ricavato dalle ore: presente, assente tutto il giorno, entrato in ritardo (da che ora), uscito in anticipo (da che ora).

**AC-08 · Totale delle assenze**
Dato che apro uno studente di una mia classe, quando guardo le sue assenze, allora vedo il totale di ore e di giorni di assenza nel quadrimestre, e le ore di assenza nella mia materia sul totale delle ore previste dall'orario.

**AC-09 · Registro delle assenze della classe**
Dato che insegno in una classe, quando apro le assenze, allora vedo quelle di tutti gli studenti della classe, segnate da tutti i docenti, per giorno e per ora.

**AC-10 · Il Direttore vede tutto**
Dato che sono autenticato come Direttore, quando consulto le assenze, allora vedo quelle di tutta la scuola, filtrabili per classe, studente e periodo, in sola lettura. Fra le segnalazioni della vista d'insieme (DIR-03) vedo le ore di lezione passate senza appello *(proposta)*.

**AC-11 · Giustificazione**
Dato che uno studente mi presenta nella mia ora la giustificazione firmata su carta, quando la registro, allora segno come "giustificata" l'assenza, il ritardo o l'uscita a cui si riferisce. Il sistema registra chi l'ha giustificata e quando. Per un ritardo, la giustificazione la registra il docente dell'ora in cui lo studente entra.

**AC-12 · Salvataggio non riuscito**
Dato che la connessione cade mentre salvo l'appello, quando il salvataggio fallisce, allora le assenze che ho segnato restano sulla pagina, vedo un avviso e posso riprovare.

**AC-13 · Solo i docenti fanno l'appello e giustificano**
Dato che sono autenticato come Studente, quando provo a segnare, correggere o giustificare un'assenza (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione. Lo stesso vale per un Docente che prova a farlo in un'ora non sua.

**AC-14 · Assenze da giustificare**
Dato che apro l'appello della mia ora, quando guardo l'elenco, allora accanto a ogni studente vedo se ha assenze, ritardi o uscite ancora da giustificare, e da lì registro la giustificazione (AC-11).

**AC-15 · Giustificazione sbagliata**
Dato che ho segnato come giustificata l'assenza sbagliata, quando la correggo, allora torna "da giustificare" e il cambio resta nello storico, come per le altre correzioni (AC-06).

---

## Regole e dati

| Dato | Regola |
| --- | --- |
| Assenza | Per studente, giorno e ora di lezione (DIR-06) |
| Stato della giornata | Ricavato dalle ore: assente tutto il giorno, ritardo, uscita anticipata, presente |
| Ritardo | Assente nelle prime ore, poi presente |
| Uscita anticipata | Presente nelle prime ore, poi assente |
| Totali | Ore e giorni di assenza per quadrimestre; ore di assenza per materia sulle ore previste |
| Giustificazione | `da giustificare` → `giustificata`, con docente, data e ora. La registra il docente dell'ora in cui lo studente la presenta |

- Uno studente assente per un'ora, ma presente prima e dopo, risulta "assente quell'ora" nel riepilogo della giornata.
- Le assenze sono dati personali di minori (VIN-07): le vedono lo studente, i docenti della sua classe e il Direttore.
- Ordine di grandezza: un appello per ogni ora di ogni classe, circa 690 appelli a settimana; al cambio d'ora fino a 23 appelli nello stesso minuto, ognuno leggero.

## Fuori perimetro di questa storia

- Inserimento dell'orario → **DIR-06**
- Consultazione delle assenze da parte dello studente → **STU-06**
- Giustificazione online da parte dello studente o della famiglia: la giustificazione arriva su carta e la registra il docente (AC-11)
- Avviso alle famiglie (non ci sono account per i genitori)
- Calcolo automatico della validità dell'anno (limite di assenze): ScuolaChill mostra i totali, non decide
- Supplenze *(da decidere, vedi DIR-06)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Vincolo | VIN-07 | GDPR: le assenze sono dati di minori |
| NFR | NFR-03 | Controllo ruolo, classe e ora lato backend (AC-04, AC-11, AC-13) |
| NFR | NFR-09 | Elenchi paginati (AC-09, AC-10) ed errori uniformi |
| Storia | DIR-06 | L'appello si fa nelle ore dell'orario (AC-01, AC-04) |
| Storia | DIR-03 | Ore senza appello fra le segnalazioni (AC-10) |
| Storia | DOC-03 | Stesso storico delle modifiche dei voti (AC-06) |
| Storia | STU-06 | Lo studente vede le sue assenze |

## Domande aperte per il team

1. Fino a quando si può fare l'appello dimenticato (AC-05) e correggere un'assenza (AC-06)? *(proposta: stesso giorno per l'appello, 7 giorni per le correzioni)*
2. Vi servono le ore senza appello fra le segnalazioni del Direttore (AC-10)?
3. Il Direttore deve poter correggere le assenze, o solo vederle?
4. Entro quanti giorni va giustificata un'assenza? Se la giustificazione non arriva, il Direttore la vede fra le segnalazioni (DIR-03)?
