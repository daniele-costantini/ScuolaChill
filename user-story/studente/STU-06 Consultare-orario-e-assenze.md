# STU-06 · Consultare orario e assenze

**Ruolo:** Studente (ARC-003)

**Storia**

Come Studente, voglio vedere l'orario della mia classe e le mie assenze, per sapere che lezione ho e quante ore di assenza ho accumulato.

---

## Acceptance criteria della traccia

> 💡 Storia aggiunta dal team: la traccia non la prevede, quindi non ci sono AC della traccia da riportare.

## AC aggiunti dal team

**AC-01 · Orario della mia classe**
Dato che sono autenticato come Studente e iscritto a una classe, quando apro la sezione Orario, allora vedo l'orario della settimana, giorno per giorno e ora per ora, con materia e docente.

**AC-02 · Oggi in evidenza**
Dato che apro l'orario durante la giornata, quando lo guardo, allora il giorno di oggi e l'ora in corso sono messi in evidenza.

**AC-03 · Orario cambiato**
Dato che il Direttore ha cambiato l'orario da una certa data (DIR-06 AC-05), quando apro la sezione Orario, allora vedo l'orario nuovo e un avviso con la data da cui vale.

**AC-04 · Le mie assenze**
Dato che apro la sezione Assenze, quando la consulto, allora vedo, dalla più recente, le giornate in cui sono stato assente, entrato in ritardo o uscito in anticipo, con le ore e le materie che ho perso e se sono "giustificate" o "da giustificare".

**AC-05 · Totali**
Dato che apro la sezione Assenze, quando guardo il riepilogo, allora vedo il totale di ore e di giorni di assenza del quadrimestre e, per ogni materia, le ore di assenza sul totale delle ore previste.

**AC-06 · Assenze per quadrimestre**
Dato che l'anno è diviso in due quadrimestri, quando apro la sezione Assenze, allora vedo il quadrimestre in corso e posso passare all'altro.

**AC-07 · Assenza corretta**
Dato che un docente ha corretto una mia assenza (DOC-07 AC-06), quando la guardo, allora vedo la versione nuova, segnata come "modificata".

**AC-08 · Nessuna assenza**
Dato che non ho assenze, quando apro la sezione, allora vedo un messaggio che lo dice, non una pagina vuota.

**AC-09 · Studente senza classe**
Dato che il Direttore non mi ha ancora assegnato a una classe (DIR-02 AC-04), quando apro la sezione Orario, allora vedo un messaggio che mi spiega che non sono ancora in una classe, non un errore.

**AC-10 · Cambio di classe** *(collegato alla proposta DIR-04 AC-08)*
Dato che il Direttore mi ha trasferito in un'altra classe, quando apro le sezioni, allora vedo l'orario della nuova classe; le mie assenze restano tutte, con l'indicazione della classe in cui le ho fatte.

**AC-11 · Solo le mie assenze**
Dato che sono autenticato come Studente, quando provo a vedere le assenze di un compagno (anche cambiando l'ID nell'indirizzo o chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

**AC-12 · Usabile da iPad, PC e smartphone** *(NFR-11)*
Dato che apro orario e assenze dall'iPad a scuola, oppure dal PC o dal telefono a casa, quando li consulto, allora la pagina si adatta allo schermo senza zoomare né scorrere in orizzontale.

**AC-13 · Sola lettura**
Dato che sono autenticato come Studente, quando consulto orario e assenze, allora non posso modificarli né giustificare da solo le assenze: la giustificazione la registra il docente quando gliela porto su carta (DOC-07 AC-11).

---

## Regole e dati

| Dato mostrato | Regola |
| --- | --- |
| Orario | Quello della classe dello studente, valido oggi (DIR-06) |
| Stato della giornata | Assente tutto il giorno, ritardo, uscita anticipata, assente in alcune ore (DOC-07 AC-07) |
| Ore perse | Ora e materia di ogni ora di assenza |
| Totali | Ore e giorni del quadrimestre; per materia, ore di assenza sulle ore previste |
| Classe | Indicata solo per le assenze fatte in una classe diversa da quella attuale (AC-10) |

- ScuolaChill mostra i totali, ma non dice se lo studente ha superato il limite di assenze per la validità dell'anno.
- Ordine di grandezza: l'orario è una delle pagine più aperte, ma cambia raramente; è una lettura leggerissima.

## Fuori perimetro di questa storia

- Inserimento dell'orario → **DIR-06**
- Appello e correzione delle assenze → **DOC-07**
- Giustificazione online da parte dello studente: la registra il docente (DOC-07 AC-11)
- Avviso del limite di assenze per la validità dell'anno *(da decidere)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Vincolo | VIN-07 | GDPR: le assenze sono dati di minori (AC-11) |
| NFR | NFR-03 | Controllo ruolo e studente lato backend (AC-11) |
| NFR | NFR-09 | Elenco assenze paginato (AC-04) ed errori uniformi (AC-11) |
| NFR | NFR-11 | Usabile da iPad, PC e smartphone (AC-12) |
| Storia | DIR-06 | L'orario della classe |
| Storia | DOC-07 | Le assenze segnate dai docenti |
| Storia | DIR-04 | Trasferimento fra classi (AC-10) |

## Domande aperte per il team

1. Lo studente deve vedere un avviso quando si avvicina al limite di assenze per la validità dell'anno? Richiede di sapere qual è il limite e le eventuali deroghe.
2. Nell'orario serve anche l'orario delle singole ore (es. 8:10-9:10), o bastano giorno e numero dell'ora?
