# STU-03 · Consultare i propri voti

**Ruolo:** Studente (ARC-003)

**Storia**

Come Studente, voglio consultare i miei voti raggruppati per materia, con la media di ciascuna, per sapere come sto andando e dove devo recuperare.

---

## Acceptance criteria della traccia

> 💡 Riportare qui gli AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Voti raggruppati per materia**
Dato che sono autenticato come Studente, quando apro la sezione Voti, allora vedo l'elenco delle mie materie e, per ognuna, la media e il numero di voti. Le materie senza voti compaiono con la scritta "nessun voto".

**AC-02 · Dettaglio di una materia**
Dato che ho scelto una materia, quando ne consulto i voti, allora li vedo dal più recente, ciascuno con voto, data, tipo di prova (scritto, orale, pratico), docente e commento, se c'è (DOC-03 AC-05, AC-09).

**AC-03 · Solo i voti pubblicati**
Dato che il docente sta ancora correggendo una verifica, quando apro i miei voti, allora non vedo quelli non ancora pubblicati, neanche chiamando direttamente l'API. Li vedo appena il docente li pubblica (DOC-03 AC-04).

**AC-04 · Media della materia**
Dato che ho almeno un voto in una materia, quando ne guardo la media, allora vedo la media aritmetica dei voti pubblicati di quel quadrimestre, arrotondata a due decimali *(proposta: tutti i voti pesano uguale, come in DOC-03)*.

**AC-05 · Voti per quadrimestre** *(collegato alla proposta DOC-03 AC-12)*
Dato che l'anno è diviso in due quadrimestri, quando apro la sezione Voti, allora vedo il quadrimestre in corso e posso passare all'altro; medie e voti si aggiornano di conseguenza.

**AC-06 · Voto insufficiente in evidenza**
Dato che ho un voto o una media sotto il 6, quando li guardo, allora sono evidenziati in modo diverso dai sufficienti, non solo con il colore (per esempio con un'icona), così si capisce anche con lo schermo in pieno sole o per chi non distingue i colori.

**AC-07 · Voto nuovo**
Dato che il docente ha pubblicato un voto dopo il mio ultimo accesso, quando apro la sezione Voti, allora quel voto è segnato come "nuovo" e la materia mostra quanti voti nuovi contiene *(proposta, da confermare insieme a STU-01 AC-06)*.

**AC-08 · Voto di una verifica online**
Dato che un voto viene da una verifica svolta su ScuolaChill (DOC-02), quando lo apro, allora posso vedere la verifica con le mie risposte, le risposte corrette e i punti presi per ogni domanda (STU-02 AC-13).

**AC-09 · Verifica non svolta**
Dato che non ho svolto una verifica online (STU-02 AC-14), quando apro i voti della materia, allora la vedo segnata come "non svolta", senza voto e senza effetto sulla media, finché il docente non mi inserisce un voto di recupero (DOC-03 AC-08).

**AC-10 · Voto modificato o eliminato**
Dato che il docente ha corretto un voto (DOC-03 AC-10), quando lo guardo, allora vedo il voto nuovo, segnato come "modificato" con la data della modifica. Se il docente lo ha eliminato (DOC-03 AC-11), non lo vedo più e non conta nella media.

**AC-11 · Riepilogo generale**
Dato che apro la sezione Voti, quando guardo il riepilogo in alto, allora vedo la media generale del quadrimestre (media delle medie delle materie) e quante materie sono insufficienti *(proposta, da confermare)*.

**AC-12 · Nessun voto**
Dato che non ho ancora nessun voto, quando apro la sezione Voti, allora vedo un messaggio che lo dice, non una pagina vuota né un errore.

**AC-13 · Cambio di classe** *(collegato alla proposta DIR-04 AC-08)*
Dato che il Direttore mi ha trasferito in un'altra classe, quando apro i miei voti, allora continuo a vedere anche quelli presi nella classe precedente, con l'indicazione della classe in cui li ho presi, e contano nella media della materia.

**AC-14 · Usabile da iPad, PC e smartphone** *(NFR-11)*
Dato che apro i voti dall'iPad a scuola, oppure dal PC o dal telefono a casa, quando li consulto, allora la pagina si adatta allo schermo e posso leggere voti, medie e commenti senza zoomare né scorrere in orizzontale.

**AC-15 · Solo i miei voti**
Dato che sono autenticato come Studente, quando provo a vedere i voti di un altro studente (anche cambiando l'ID nell'indirizzo o chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione. Non posso inserire, modificare né eliminare voti (DOC-03 AC-14).

---

## Regole e dati

| Dato mostrato | Regola |
| --- | --- |
| Voto | Da 1 a 10, passo 0,5 *(proposta DOC-03 AC-01)*, mostrato con la virgola (es. 6,5) |
| Data | Data della prova, formato italiano |
| Tipo di prova | Scritto, orale o pratico |
| Docente | Nome e cognome di chi ha assegnato il voto |
| Commento | Se presente |
| Classe | Indicata solo per i voti presi in una classe diversa da quella attuale (AC-13) |
| Media della materia | Media aritmetica dei voti pubblicati del quadrimestre, due decimali |
| Media generale | Media delle medie delle materie con almeno un voto *(proposta)* |

- Lo studente vede solo voti in stato `pubblicato` (DOC-03, Stati del voto).
- Le medie si calcolano con le stesse regole della vista d'insieme del Direttore (DIR-03): uno studente e il Direttore devono vedere la stessa media.
- Lo storico delle modifiche di un voto resta al docente e al Direttore: lo studente vede solo che il voto è stato modificato (AC-10).
- Ordine di grandezza: circa 30-40 voti per studente a quadrimestre; a fine quadrimestre (350 utenti concorrenti) è una delle pagine più aperte.

## Fuori perimetro di questa storia

- Assegnazione, modifica ed eliminazione dei voti → **DOC-03**
- Andamento dei voti visto dal Direttore → **DIR-03**
- Pagella e voto di fine quadrimestre *(da decidere, vedi DOC-03)*
- Accesso dei genitori ai voti (le comunicazioni con le famiglie sono fuori dal perimetro del PRD)
- Notifiche quando arriva un voto nuovo *(da decidere)*
- Grafici dell'andamento nel tempo *(da decidere)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Decisione aperta | Scala dei voti | I voti e le medie mostrati dipendono dalla proposta DOC-03 AC-01 |
| NFR | NFR-02 | HTTPS: i voti viaggiano cifrati |
| NFR | NFR-03 | Controllo ruolo lato backend: lo studente vede solo i propri voti (AC-15) |
| NFR | NFR-09 | Elenco voti paginato (AC-02) ed errori uniformi (AC-15) |
| NFR | NFR-11 | Usabile da iPad, PC e smartphone (AC-14) |
| Storia | DOC-03 | I voti pubblicati dal docente, con commento, modifiche ed eliminazioni |
| Storia | STU-02 | Le risposte della verifica online dietro al voto (AC-08, AC-09) |
| Storia | DIR-03 | Stesse regole di calcolo delle medie |
| Storia | DIR-04 | Trasferimento fra classi (AC-13) |

## Domande aperte per il team

1. Serve la media generale (AC-11), o rischia di essere fraintesa come voto di fine anno?
2. Lo studente deve vedere anche il voto precedente quando un voto viene modificato (AC-10)? *(proposta: no, vede solo che è stato modificato)*
3. I voti di una materia che la classe nuova non ha (AC-13) dove compaiono? *(proposta: nella materia, con l'indicazione della classe precedente)*
4. Serve un requisito implicito del tipo "un voto pubblicato non sparisce mai senza traccia"? È l'esempio dell'intervista nel PRD e qui sarebbe verificabile (AC-10).
