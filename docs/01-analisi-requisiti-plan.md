
# 01 – Analisi dei requisiti (Plan)

In questa fase ho utilizzato OpenCode per analizzare l'idea iniziale di Splitly, chiedendo all'agente di individuare eventuali ambiguità o informazioni mancanti nella mia richiesta.

Attraverso le sue domande ho chiarito i requisiti e definito le regole principali dell'app, prima di passare alla progettazione generale.

## Confronto con OpenCode

Di seguito alcuni scambi della conversazione originale. Il primo prompt è riportato integralmente, mentre nei successivi ho selezionato soltanto gli estratti più significativi.

<details>
<summary>💬 Clicca qui per visualizzare i prompt e le risposte di OpenCode</summary>

<h3 align="center">1. Idea iniziale e primo chiarimento</h3>

**👤 Io — Prompt iniziale**

```text
## Contesto
Voglio realizzare una web app mobile-first chiamata Splitly.

## Obiettivo
L'applicazione deve permettere agli utenti di dividere un conto in parti uguali tra più persone, registrare quanto ciascuno ha versato e calcolare l'eventuale resto spettante a ogni partecipante.

## Vincoli
- Non aggiungere funzionalità non richieste.
- Per ora non valutare le tecnologie da utilizzare.
- Non scrivere codice né creare o modificare file.

## Richiesta
- Analizza la mia idea e segnalami eventuali aspetti poco chiari o informazioni mancanti.
- Se necessario, fammi una domanda alla volta senza prendere decisioni al posto mio.

## Output
- Utilizza un linguaggio semplice e risposte brevi, preferibilmente entro 5 righe.
```

**🤖 OpenCode — Risposta**

```text
L’idea è chiara: dividere il conto in quote uguali, registrare i versamenti e calcolare il resto di ciascuno.

Il primo punto da chiarire riguarda chi versa meno della propria quota: l’app deve mostrare quanto gli manca da pagare oppure permettere che un altro partecipante copra la differenza?
```

---

<h3 align="center">2. Gestione dei versamenti insufficienti</h3>

**👤 Io — Estratto dalla sezione "Chiarimenti"**

```text
Gestione di un versamento inferiore alla quota individuale

- Se una persona versa un importo inferiore alla propria quota, l'applicazione deve indicare quanto deve ancora aggiungere.

Ad Esempio:
- Se Pippo deve pagare 20 € ma ne versa 15 €, l'applicazione deve segnalare che Pippo deve aggiungere ancora 5 €.
```

**🤖 OpenCode — Risposta**

```text
Il chiarimento è chiaro: chi versa meno della propria quota deve vedere quanto deve ancora aggiungere.

Resta da definire come gestire i centesimi quando il conto non si divide esattamente.

Ad esempio, dividendo 10 € tra 3 persone, come vuoi assegnare il centesimo residuo, dato che tre quote da 3,33 € totalizzano 9,99 €?
```

---

<h3 align="center">3. Gestione dell'arrotondamento</h3>

**👤 Io — Estratto dalla sezione "Chiarimenti"**

```text
Gestione centesimo residuo

- Quando il conto non è divisibile esattamente tra i partecipanti, arrotonda la quota individuale per eccesso al centesimo, informando gli utenti dell'arrotondamento effettuato.
- Segnala anche l'eventuale importo in eccesso generato dall'arrotondamento. Saranno poi gli utenti a decidere come gestirlo.
```

**🤖 OpenCode — Risposta**

```text
La regola è chiara: con un conto di 10 € e 3 persone, ciascuno deve 3,34 €; l’app segnala l’arrotondamento e i 0,02 € complessivi in eccesso.

Resta un punto da confermare: il resto di ciascuno deve essere calcolato come differenza tra quanto ha versato e la quota arrotondata? Ad esempio, versando 5 €, riceverebbe 1,66 €.
```

---

<h3 align="center">4. Conferma del calcolo del resto</h3>

**👤 Io — Estratto dalla sezione "Chiarimenti"**

```text
Calcolo del resto con gestione dei centesimi residui

- Confermo che il resto di ciascuno deve essere calcolato come differenza tra quanto ha versato e la quota arrotondata.
- Alla fine, l'app deve mostrare gli eventuali centesimi in eccesso generati dall'arrotondamento, lasciando agli utenti la decisione su come gestirli.
```

**🤖 OpenCode — Estratto della risposta**

```text
I requisiti sono sufficientemente chiari per definire il funzionamento di base.

- Quota uguale per tutti, arrotondata per eccesso al centesimo, con avviso dell’arrotondamento.
- Per ciascuno: importo ancora da aggiungere oppure resto rispetto alla quota arrotondata.
- Eccesso complessivo da arrotondamento mostrato alla fine, lasciandone la gestione agli utenti.
```

</details>

## Decisioni finali

| Aspetto | Come funzionerà Splitly |
|---|---|
| **Obiettivo** | Dividere un conto tra amici in parti uguali, calcolando quanto ciascuno deve pagare o ricevere come resto. |
| **Versamenti** | L'app permette di registrare quanto ha versato ciascuna persona. |
| **Importo insufficiente** | Se una persona ha versato meno della propria quota, l'app indica quanto deve ancora aggiungere. |
| **Resto individuale** | Se una persona ha versato più della propria quota, l'app mostra il resto che le spetta, calcolato rispetto alla quota arrotondata. |
| **Arrotondamento** | Se il conto non è divisibile esattamente, la quota di tutti viene arrotondata per eccesso al centesimo, avvisando gli utenti. |
| **Centesimi in eccesso** | Alla fine, l'app mostra l'eccedenza complessiva generata dall'arrotondamento, lasciando agli utenti la decisione su come gestirla. |

---

Una volta chiariti questi aspetti, ho confermato i requisiti e sono passata alla [progettazione generale](02-progettazione-generale-plan.md).
