# DIR-06 · Inserire l'orario delle classi

**Ruolo:** Direttore (ARC-001)

**Storia**

Come Direttore, voglio inserire l'orario settimanale di ogni classe, con materia e docente per ogni ora, perché studenti e docenti sappiano dove devono essere e i docenti possano fare l'appello nelle loro ore.

---

## Acceptance criteria della traccia

> 💡 Storia aggiunta dal team: la traccia non la prevede, quindi non ci sono AC della traccia da riportare.

## AC aggiunti dal team

**AC-01 · Ore di lezione della scuola**
Dato che sono autenticato come Direttore, quando imposto le ore di lezione, allora indico per ogni giorno della settimana quante ore ci sono e l'ora di inizio e di fine di ognuna. Valgono per tutte le classi (vedi l'orario scolastico nella prima parte del PRD).

**AC-02 · Orario di una classe**
Dato che apro una classe, quando compilo l'orario, allora per ogni giorno e ora scelgo una materia della classe e il docente che la insegna in quella classe (DIR-04). Un'ora può restare libera.

**AC-03 · Un docente in una sola classe per ora**
Dato che sto assegnando un docente a un'ora, quando quel docente è già in un'altra classe alla stessa ora, allora il sistema non salva e mi dice in quale classe è già impegnato.

**AC-04 · Ore settimanali per materia**
Dato che sto compilando l'orario di una classe, quando lo guardo, allora vedo quante ore a settimana ha ogni materia, così controllo che corrispondano a quelle previste.

**AC-05 · Modifica da una data**
Dato che l'orario di una classe cambia durante l'anno, quando lo modifico, allora scelgo da che giorno vale il nuovo orario. Le ore già passate, e le assenze registrate in quelle ore (DOC-07), restano con l'orario di allora.

**AC-06 · Orario del docente**
Dato che ho inserito gli orari delle classi, quando apro un docente, allora vedo il suo orario settimanale, ricavato da quelli delle classi in cui insegna.

**AC-07 · Classe senza orario**
Dato che una classe non ha ancora l'orario, quando apro la vista d'insieme (DIR-03), allora la classe compare fra le segnalazioni, perché senza orario i docenti non possono fare l'appello.

**AC-08 · Docente o materia cambiati**
Dato che in DIR-04 cambio il docente di una materia in una classe, quando salvo, allora il sistema mi propone di aggiornare l'orario, da una data che scelgo (AC-05), mettendo il nuovo docente al posto del vecchio.

**AC-09 · Solo il Direttore inserisce l'orario**
Dato che sono autenticato come Docente o Studente, quando provo a creare o modificare un orario (anche chiamando direttamente l'API), allora il sistema rifiuta la richiesta con errore di autorizzazione.

---

## Regole e dati

| Campo | Obbligatorio | Regola |
| --- | --- | --- |
| Ore di lezione | Sì | Per ogni giorno: numero di ore, inizio e fine di ognuna |
| Classe | Sì | Una classe esistente (DIR-04) |
| Giorno e ora | Sì | Fra le ore di lezione impostate (AC-01) |
| Materia | No (ora libera) | Fra le materie della classe |
| Docente | Sì, se c'è la materia | Il docente che insegna quella materia nella classe (DIR-04) |
| Valido dal | Sì | Data da cui vale l'orario (AC-05) |

- L'orario è settimanale e si ripete uguale ogni settimana finché non cambia (AC-05).
- Ordine di grandezza: 23 classi × circa 30 ore a settimana ≈ 690 ore da inserire a inizio anno, poi poche modifiche.

## Fuori perimetro di questa storia

- Consultazione dell'orario da parte di studenti e docenti → **STU-06**, **DOC-07**
- Generazione automatica dell'orario
- Supplenze e cambi d'ora per un solo giorno *(da decidere)*
- Aule e laboratori
- Giorni senza lezione (festività, uscite didattiche): si avvisano con le comunicazioni (DIR-05)

## Collegamenti

| Tipo | ID | Note |
| --- | --- | --- |
| NFR | NFR-03 | Controllo ruolo lato backend (AC-09) |
| NFR | NFR-09 | Errori uniformi (AC-03) |
| Storia | DIR-04 | Materie e docenti di ogni classe (AC-02, AC-08) |
| Storia | DIR-03 | Classi senza orario fra le segnalazioni (AC-07) |
| Storia | DOC-07 | L'appello si fa nelle ore dell'orario |
| Storia | STU-06 | Lo studente consulta l'orario |

## Domande aperte per il team

1. Servono le supplenze, cioè un altro docente per una sola ora di un giorno? Senza, il supplente non può fare l'appello.
2. Le ore di lezione sono uguali per tutte le classi (AC-01), o alcune classi hanno orari diversi?
3. Il Direttore deve poter copiare l'orario di una classe su un'altra, per fare prima a inizio anno?
