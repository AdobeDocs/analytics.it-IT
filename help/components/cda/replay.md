---
title: Funzionamento delle riproduzioni
description: Comprendere il concetto di "ripetizione" in Analytics tra dispositivi
exl-id: 0b7252ff-3986-4fcf-810a-438d9a51e01f
feature: CDA
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 15%

---

# Funzionamento delle riproduzioni

Analytics tra dispositivi effettua due passaggi sui dati in una suite di rapporti virtuale:

* **Live-stitching**: CDA tenta di unire ogni hit nel momento in cui arriva. I nuovi dispositivi della suite di rapporti che non hanno mai effettuato l’accesso in genere non vengono uniti a questo livello. I dispositivi già riconosciuti vengono uniti immediatamente.
* **Riproduci**: circa una volta alla settimana, CDA &quot;riproduce&quot; i dati in base a identificatori univoci appresi. In questa fase vengono uniti nuovi dispositivi della suite di rapporti.

## Tabella di esempio

Le tabelle seguenti illustrano entrambi i metodi CDA ([Unione basata sui campi](field-based-stitching.md) e [Device Graph](device-graph.md)) calcola il numero di persone univoche:

### Live-stitching

Non appena viene raccolto un hit, CDA tenta di unirlo ai dispositivi noti. Prendi in considerazione l’esempio seguente, in cui Bob utilizza due dispositivi.

*Dati visualizzati nel giorno in cui vengono raccolti:*

| Marca temporale | ECID | eVar1 o CustomerID | Spiegazione dell’hit | Metrica delle persone (cumulativa) utilizzo di Device Graph | Metrica delle persone (cumulativa) con unione basata sui campi |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sul suo computer desktop, non autenticato | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob accede al desktop | `1` (246) | `2` (246 e Bob) |
| `3` | `3579` | - | Bob sul suo dispositivo mobile, non autenticato | `2` 246 e 3579 | `3` (246, Bob e 3579) |
| `4` | `3579` | `Bob` | Bob accede su dispositivi mobili | `2` 246 e 3579 | `3` (246, Bob e 3579) |
| `5` | `246` | - | Bob accede di nuovo al sito sul desktop, senza essersi autenticato | `2` 246 e 3579 | `3` (246, Bob e 3579) |
| `6` | `246` | `Bob` | Bob accede nuovamente tramite desktop | `2` 246 e 3579 | `3` (246, Bob e 3579) |
| `7` | `3579` | - | Bob accede nuovamente al tuo sito su dispositivi mobili | `2` 246 e 3579 | `3` (246, Bob e 3579) |
| `8` | `3579` | `Bob` | Bob accede nuovamente tramite cellulare | `2` 246 e 3579 | `3` (246, Bob e 3579) |

Gli hit non autenticati e autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente).

* **Se utilizzi il grafico dei dispositivi,** gli hit non autenticati sui dispositivi riconosciuti sono live-stitched una volta che un cluster viene pubblicato dal grafico dei dispositivi. La pubblicazione dei cluster richiede da tre ore a due settimane.

  Quando viene pubblicato un cluster, viene aggiunta anche una terza persona cumulativa. Questa terza persona rappresenta il cluster stesso, oltre ai singoli dispositivi. Questa terza &quot;persona&quot; rimane finché i dati non vengono riprodotti.

  L’attribuzione funziona tra dispositivi solo dopo la pubblicazione di un cluster e, anche in questo caso, funziona solo live-stitching da quel momento in poi. Nell’esempio precedente, nessuno degli hit è ancora unito tra dispositivi. L’attribuzione tra dispositivi sugli hit esistenti funziona solo dopo la ripetizione dell’unione.
* **Se utilizzi l’unione basata sui campi,** gli hit non autenticati sui dispositivi riconosciuti sono live-stitched da quel momento in poi.

  L’attribuzione funziona non appena la variabile personalizzata di identificazione si collega a un dispositivo. Nell’esempio precedente, tutti gli hit ad eccezione di 1 e 3 sono live-stitched (utilizzano tutti `Bob` identificatore). L’attribuzione funziona sugli hit 1 e 3 dopo la ripetizione dell’unione.

>[!NOTE]
>
>Gli hit con marca temporale superiore a 12 ore non vengono uniti nel flusso live. Tuttavia, questi hit sono inclusi nell’unione di ripetizione, purché rientrino nell’intervallo di lookback di ripetizione.

### Ripeti unione

La ripetizione avviene ogni giorno o ogni settimana, a seconda di come hai richiesto la configurazione di CDA. Durante la ripetizione, CDA tenta di aggiornare i dati storici all’interno di un intervallo di lookback definito:

* La ripetizione giornaliera utilizza un intervallo di lookback di 1 giorno
* La ripetizione settimanale utilizza un intervallo di lookback di 7 giorni.

Se un dispositivo invia inizialmente i dati mentre non è autenticato e poi effettua l’accesso, CDA collega gli hit non autenticati alla persona corretta. La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla ripetizione dei dati.

*Gli stessi dati dopo la ripetizione:*

| Marca temporale | ECID | eVar1 o CustomerID | Spiegazione dell’hit | Metrica delle persone (cumulativa) utilizzo di Device Graph | Metrica delle persone (cumulativa) con unione basata sui campi |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sul suo computer desktop, non autenticato | `1` (Cluster1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob accede al desktop | `1` (Cluster1) | `1` (Bob) |
| `3` | `3579` | - | Bob sul suo dispositivo mobile, non autenticato | `1` (Cluster1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob accede su dispositivi mobili | `1` (Cluster1) | `1` (Bob) |
| `5` | `246` | - | Bob accede di nuovo al sito sul desktop, senza essersi autenticato | `1` (Cluster1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob accede nuovamente tramite desktop | `1` (Cluster1) | `1` (Bob) |
| `7` | `3579` | - | Bob accede nuovamente al tuo sito su dispositivi mobili | `1` (Cluster1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob accede nuovamente tramite cellulare | `1` (Cluster1) | `1` (Bob) |
