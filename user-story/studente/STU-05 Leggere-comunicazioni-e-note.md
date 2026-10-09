# STU-05 · Leggere comunicazioni e note disciplinari

**Ruolo:** Studente (ARC-003)

**Storia**

Come Studente, voglio leggere le comunicazioni della scuola e dei miei docenti e vedere le mie note disciplinari, per sapere cosa succede e cosa mi è stato segnalato.

---

## Acceptance criteria della traccia

> 💡 Storia aggiunta dal team: la traccia non la prevede, quindi non ci sono AC della traccia da riportare.

## AC aggiunti dal team

**AC-01 · Elenco delle comunicazioni**
Dato che sono autenticato come Studente, quando apro la sezione Comunicazioni, allora vedo quelle a tutta la scuola, a tutti gli studenti e alla mia classe, dalla più recente, con quelle in evidenza in cima, in un elenco paginato.

**AC-02 · Dettaglio di una comunicazione**
Dato che apro una comunicazione, quando la leggo, allora vedo titolo, testo, mittente, data e, se c'è, l'allegato o il link (DIR-05 AC-04, DOC-05 AC-04).

**AC-03 · Comunicazione nuova**
Dato che una comunicazione è arrivata e non l'ho ancora aperta, quando guardo l'elenco, allora è segnata "nuova" e la sezione mostra quante comunicazioni nuove ci sono.

**AC-04 · Comunicazione modificata o eliminata**
Dato che il mittente ha modificato o eliminato una comunicazione, quando ricarico l'elenco, allora vedo la versione nuova, segnata come "modificata", oppure la comunicazione non c'è più.

**AC-05 · Le mie note**
Dato che sono autenticato come Studente, quando apro la sezione Note, allora vedo le mie note e quelle date a tutta la mia classe, dalla più recente, con data, docente e motivo.

**AC-06 · Nota modificata o annullata**
Dato che il docente ha modificato o annullato una mia nota (DOC-06 AC-06, AC-07), quando la guardo, allora la vedo segnata come "modificata" oppure "annullata".

**AC-07 · Solo le mie note**
Dato che sono autenticato come Studente, quando provo a vedere le note di un compagno (anche cambiando l'ID nell'indirizzo o chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

**AC-08 · Nessuna comunicazione o nota**
Dato che non ho comunicazioni o note, quando apro la sezione, allora vedo un messaggio che lo dice, non una pagina vuota.

**AC-09 · Studente senza classe**
Dato che il Direttore non mi ha ancora assegnato a una classe (DIR-02 AC-04), quando apro la sezione Comunicazioni, allora vedo comunque quelle a tutta la scuola e a tutti gli studenti.

**AC-10 · Cambio di classe** *(proposta, da confermare)*
Dato che il Direttore mi ha trasferito in un'altra classe (DIR-04 AC-08), quando apro le sezioni, allora vedo le comunicazioni della nuova classe e non più quelle della precedente; le mie note restano tutte, con la classe in cui le ho prese.

**AC-11 · Usabile da iPad, PC e smartphone** *(NFR-11)*
Dato che apro comunicazioni e note dall'iPad a scuola, oppure dal PC o dal telefono a casa, quando le leggo, allora la pagina si adatta allo schermo senza zoomare né scorrere in orizzontale.

**AC-12 · Sola lettura**
Dato che sono autenticato come Studente, quando leggo comunicazioni e note, allora non posso rispondere, modificarle né scriverne di nuove.

---

## Regole e dati

| Dato mostrato | Regola |
| --- | --- |
| Comunicazioni | A tutta la scuola, a tutti gli studenti e alla classe dello studente |
| Mittente | Direttore o nome e cognome del docente |
| Nuova | Non ancora aperta dallo studente |
| Note | Le note dello studente e quelle a tutta la sua classe (DOC-06 AC-04) |
| Classe della nota | Indicata solo per le note prese in una classe diversa da quella attuale (AC-10) |

- Lo studente vede solo le note che lo riguardano (DOC-06 AC-05).
- Ordine di grandezza: la sezione Comunicazioni si apre soprattutto all'inizio della giornata; è una lettura leggera.

## Fuori perimetro di questa storia

- Pubblicare comunicazioni → **DIR-05**, **DOC-05**
- Segnare le note → **DOC-06**
- Rispondere alle comunicazioni o alle note
- Email e notifiche *(da decidere, come in DIR-05)*

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| Vincolo | VIN-07 | GDPR: le note sono dati delicati di minori (AC-07) |
| NFR | NFR-03 | Controllo ruolo, classe e studente lato backend (AC-07) |
| NFR | NFR-09 | Elenchi paginati (AC-01, AC-05) ed errori uniformi (AC-07) |
| NFR | NFR-11 | Usabile da iPad, PC e smartphone (AC-11) |
| Storia | DIR-05 | Comunicazioni del Direttore |
| Storia | DOC-05 | Comunicazioni dei docenti alla classe |
| Storia | DOC-06 | Le note segnate dai docenti |

## Domande aperte per il team

1. Il segno "nuova" (AC-03) va registrato come lettura, così il Direttore vede quanti l'hanno letta (DIR-05 AC-09)?
2. Dopo un trasferimento lo studente deve vedere ancora le comunicazioni della classe precedente (AC-10)? *(proposta: no)*
