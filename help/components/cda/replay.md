---
title: Funzionamento delle riproduzioni
description: Comprendere il concetto di "riproduzione" in Analisi multidispositivo
translation-type: tm+mt
source-git-commit: f3f5f82a236d376eda07d4d39e7effa60e929499
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 2%

---


# Funzionamento delle riproduzioni

Analisi multidispositivo effettua due passaggi sui dati in una suite di rapporti virtuale:

* **Stitching in tempo reale**: CDA tenta di unire ogni hit mentre arriva. In genere, i nuovi dispositivi collegati alla suite di rapporti che non hanno mai eseguito l’accesso non vengono uniti a questo livello. I dispositivi già riconosciuti vengono uniti immediatamente.
* **Riproduci**: Circa una volta alla settimana, CDA &quot;riproduce&quot; i dati in base a identificatori univoci che ha appreso. In questa fase i nuovi dispositivi della suite di rapporti diventano uniti.

## Esempio di tabella

Nelle tabelle seguenti viene illustrato come i metodi CDA ([Unione basata su campi](field-based-stitching.md) e [Grafico dispositivo](device-graph.md)) calcolano il numero di persone univoche:

### Stitching live

Non appena viene raccolto un hit, CDA tenta di unirlo a dispositivi noti. Prendi in considerazione l&#39;esempio seguente, in cui Bob utilizza due dispositivi.

*Dati visualizzati nel giorno in cui vengono raccolti:*

| Timestamp | ECID | eVar1 o CustomerID | Spiegazione dell&#39;hit | Metrica Persone (cumulativa) tramite Device Graph | Metrica Persone (cumulativa) tramite unione basata su campi |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sul suo computer desktop, non autenticato | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob accede al suo desktop | `1` (246) | `2` (246 e Bob) |
| `3` | `3579` | - | Bob sul suo dispositivo mobile, non autenticato | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `4` | `3579` | `Bob` | Bob accede sul cellulare | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `5` | `246` | - | Bob accede nuovamente al tuo sito sul desktop, non autenticato | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `6` | `246` | `Bob` | Bob accede di nuovo tramite desktop | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `7` | `3579` | - | Bob accede nuovamente al tuo sito su dispositivi mobili | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `8` | `3579` | `Bob` | Bob accede di nuovo tramite cellulare | `2` (246 e 3579) | `3` (246, Bob e 3579) |

Gli hit sia non autenticati che autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente).

* **Se utilizzi il grafico del dispositivo,** gli hit non autenticati sui dispositivi riconosciuti vengono uniti in tempo reale una volta che un cluster viene pubblicato dal grafico del dispositivo. La pubblicazione dei cluster richiede da tre ore a due settimane.

   Viene aggiunta anche una terza persona cumulativa quando viene pubblicato un cluster. Questa terza persona rappresenta il cluster stesso, oltre ai singoli dispositivi. Questa terza &quot;persona&quot; rimane finché i dati non vengono riprodotti.

   L&#39;attribuzione funziona su più dispositivi solo dopo la pubblicazione di un cluster, e anche allora solo live-stitches da quel momento in poi. Nell’esempio precedente, nessuno degli hit è ancora vincolato a diversi dispositivi. L’attribuzione tra dispositivi sugli hit esistenti non funziona fino a dopo la ripetizione dell’unione.
* **Se utilizzi l’unione basata sui campi, gli hit non autenticati su dispositivi riconosciuti vengono codificati in tempo reale da quel momento in poi.** 

   L’attribuzione funziona non appena la variabile personalizzata di identificazione si collega a un dispositivo. Nell’esempio precedente, tutti gli hit ad eccezione degli hit 1 e 3 vengono uniti in tempo reale (utilizzano tutti l’identificatore `Bob` ). L’attribuzione funziona sugli hit 1 e 3 dopo la ripetizione dell’unione.

### Ripetete l&#39;unione

La riproduzione avviene quotidianamente o settimanalmente, a seconda di come hai richiesto la configurazione di CDA. Durante la riproduzione, CDA tenta di ripristinare i dati storici all’interno di un intervallo di lookback definito:

* La riproduzione giornaliera utilizza un intervallo di lookback di 1 giorno
* La riproduzione settimanale utilizza un intervallo di lookback di 7 giorni.

Se un dispositivo invia inizialmente i dati mentre non è autenticato e successivamente effettua l’accesso, CDA collega gli hit non autenticati alla persona corretta. La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla riproduzione dei dati.

*Gli stessi dati dopo la riproduzione:*

| Timestamp | ECID | eVar1 o CustomerID | Spiegazione dell&#39;hit | Metrica Persone (cumulativa) tramite Device Graph | Metrica Persone (cumulativa) tramite unione basata su campi |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sul suo computer desktop, non autenticato | `1` (Cluster1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob accede al suo desktop | `1` (Cluster1) | `1` (Bob) |
| `3` | `3579` | - | Bob sul suo dispositivo mobile, non autenticato | `1` (Cluster1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob accede sul cellulare | `1` (Cluster1) | `1` (Bob) |
| `5` | `246` | - | Bob accede nuovamente al tuo sito sul desktop, non autenticato | `1` (Cluster1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob accede di nuovo tramite desktop | `1` (Cluster1) | `1` (Bob) |
| `7` | `3579` | - | Bob accede nuovamente al tuo sito su dispositivi mobili | `1` (Cluster1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob accede di nuovo tramite cellulare | `1` (Cluster1) | `1` (Bob) |
