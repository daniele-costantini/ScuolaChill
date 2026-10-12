# DOC-03 · Assegnare i voti

**Ruolo:** Docente (ARC-002)

**Storia**

Come Docente, voglio assegnare i voti ai miei studenti, per le verifiche svolte su ScuolaChill e per le altre prove, per tenere traccia del loro andamento e permettere a loro di vederlo.

---

## Acceptance criteria della traccia

> 💡 Riportare qui gli AC della traccia come riferimento (non si possono togliere).

1. *…*
2. *…*
3. *…*

## AC aggiunti dal team

**AC-01 · Scala dei voti** *(proposta per la decisione aperta, da confermare con il team)*
Dato che sto assegnando un voto, quando lo inserisco, allora posso scegliere solo un valore da 1 a 10 con passo di mezzo punto (1; 1,5; 2; … 10). Segni come "+" e "−" non sono ammessi. Qualsiasi altro valore viene rifiutato con un errore chiaro.

**AC-02 · Voto di una verifica online**
Dato che una verifica di DOC-02 è chiusa, quando la apro per valutarla, allora vedo per ogni studente il punteggio delle domande chiuse già calcolato, correggo le domande aperte assegnando i punti e inserisco il voto finale.

**AC-03 · Voto proposto dal punteggio** *(proposta, da confermare)*
Dato che ho corretto tutte le domande di uno studente, quando apro il suo voto, allora il sistema mi propone un voto calcolato in proporzione al punteggio (punteggio pieno = 10, arrotondato al mezzo punto). Posso accettarlo o cambiarlo.

**AC-04 · Pubblicazione dei voti di una verifica**
Dato che sto valutando una verifica, quando salvo i voti, allora restano visibili solo a me finché non li pubblico. Quando li pubblico, ogni studente vede il suo voto (STU-03).

**AC-05 · Voto per una prova fuori da ScuolaChill**
Dato che ho interrogato uno studente o fatto una verifica su carta, quando inserisco un voto indicando studente, tipo di prova (scritto, orale, pratico), data e voto, allora il voto viene salvato e lo studente lo vede subito.

**AC-06 · Voti a tutta la classe**
Dato che ho fatto una verifica su carta a tutta la classe, quando scelgo "Voti per la classe", allora vedo l'elenco degli studenti e inserisco un voto per ognuno in un'unica schermata, lasciando vuoti gli assenti.

**AC-07 · Solo le mie classi e materie**
Dato che sto assegnando un voto, quando scelgo classe e materia, allora posso scegliere solo fra le coppie classe/materia che il Direttore mi ha assegnato (DIR-04), e solo fra gli studenti iscritti a quella classe.

**AC-08 · Studente che non ha svolto la verifica**
Dato che uno studente non ha consegnato una verifica online, quando valuto la verifica, allora lo vedo segnato come "non svolta" e non gli viene assegnato nessun voto in automatico. Posso inserirgli un voto più avanti, per esempio dopo un recupero (AC-05).

**AC-09 · Commento al voto**
Dato che assegno un voto, quando aggiungo un commento, allora lo studente lo vede insieme al voto. Il commento è facoltativo.

**AC-10 · Modifica di un voto**
Dato che ho assegnato un voto, quando lo modifico, allora lo studente vede il voto aggiornato e il sistema registra chi lo ha cambiato, quando e il valore precedente. Il voto precedente non si perde.

**AC-11 · Eliminazione di un voto**
Dato che ho inserito un voto per errore (studente sbagliato, voto doppio), quando lo elimino e confermo, allora non conta più nella media e non è più visibile allo studente, ma resta registrato nello storico delle modifiche.

**AC-12 · Voti per periodo** *(proposta, da confermare)*
Dato che l'anno è diviso in due quadrimestri, quando assegno un voto, allora il voto va nel quadrimestre della sua data, e studenti e Direttore possono vedere i voti e le medie per quadrimestre (DIR-03, STU-03).

**AC-13 · Registro della classe**
Dato che apro una mia classe e materia, quando consulto i voti, allora vedo una tabella con gli studenti sulle righe, i voti in ordine di data e la media di ciascuno, con il filtro per quadrimestre.

**AC-14 · Solo il docente della classe e materia**
Dato che sono autenticato come Studente, o come Docente su una classe o materia non mia, quando provo a inserire, modificare o eliminare un voto (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Studente | Sì | Iscritto alla classe del docente |
| Classe e materia | Sì | Una coppia classe/materia assegnata al docente |
| Voto | Sì | Da 1 a 10, passo 0,5 *(proposta)* |
| Tipo di prova | Sì | Scritto, orale, pratico o compito (DOC-04) *(proposta)* |
| Data | Sì | Non nel futuro, dentro l'anno scolastico |
| Verifica | No | Collegamento alla verifica di DOC-02, se il voto viene da lì |
| Commento | No | Testo, max 500 caratteri |

**Stati del voto di una verifica online:** `da correggere` → `corretto` (visibile solo al docente) → `pubblicato`. I voti inseriti a mano (AC-05, AC-06) nascono già pubblicati.

- La media è la media aritmetica dei voti pubblicati, per materia e per quadrimestre *(proposta: tutti i voti pesano uguale)*.
- I voti non si cancellano mai davvero: modifiche ed eliminazioni restano nello storico (AC-10, AC-11).
- Se lo studente cambia classe, i voti restano con la classe in cui li ha presi (DIR-04, AC-08).
- Ordine di grandezza: con 412 studenti, circa 10 materie e 3-4 voti per materia a quadrimestre, sono circa 12.000-16.000 voti a quadrimestre.

## Fuori perimetro di questa storia

- Consultazione dei voti da parte dello studente → **STU-03**
- Andamento dei voti visto dal Direttore → **DIR-03**
- Voto di fine quadrimestre (pagella) e scrutinio *(da decidere se va in "Cosa non è incluso" del PRD)*
- Pesi diversi per tipo di prova *(da decidere)*
- Notifiche allo studente quando riceve un voto *(da decidere)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Decisione aperta | Scala dei voti | Proposta in AC-01; una volta confermata va scritta come FR nel PRD |
| NFR | NFR-03 | Controllo ruolo e classe/materia lato backend (AC-14) |
| NFR | NFR-09 | Errori uniformi (AC-01) e registro paginato (AC-13) |
| NFR | NFR-10 | Le medie di DIR-03 si calcolano su questi voti |
| Storia | DOC-02 | Il punteggio della verifica online diventa un voto (AC-02, AC-03) |
| Storia | DIR-04 | Classi, materie e trasferimento degli studenti |
| Storia | DIR-03 | Andamento dei voti per classe, materia e periodo |
| Storia | STU-03 | Lo studente vede i voti pubblicati qui |

## Domande aperte per il team

1. Confermate la scala di AC-01? In alternativa: da 1 a 10 con "+" e "−" (serve decidere quanto valgono, per esempio 6+ = 6,25), oppure solo voti interi.
2. Il voto proposto dal punteggio (AC-03) vi serve, o preferite che il docente lo inserisca sempre a mano?
3. L'anno è diviso in quadrimestri o in trimestri (AC-12)? Le date le decide il Direttore?
4. Il docente può modificare i voti di un quadrimestre già finito? *(proposta: no, solo il Direttore può sbloccarli)*
5. Un nuovo docente della materia vede e può modificare i voti dati dal precedente? *(proposta: li vede ma non li modifica)*
