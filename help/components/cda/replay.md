---
title: Come si riproduce il funzionamento
description: Comprendere il concetto di "riproduzione" in cross-device  Analytics
translation-type: tm+mt
source-git-commit: f8b70ada0a2003e43a841b6721aaa474aa9699f0
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 0%

---


# Come si riproduce il funzionamento

 Analytics esegue due passaggi sui dati in una suite di rapporti virtuale:

* **Colorazione** dal vivo: CDA tenta di cucire ogni hit mentre arriva. La rete di nuovi dispositivi alla suite di rapporti che non hanno mai registrato il tipo di interfaccia non è in genere cucita a questo livello. I dispositivi già riconosciuti vengono cuciti immediatamente.
* **Riproduci**: Circa una volta alla settimana, CDA &quot;riproduce&quot; i dati in base a identificatori univoci appresi. In questa fase vengono cuciti nuovi dispositivi della suite di rapporti.

## Esempio di tabella

Le tabelle seguenti illustrano come i metodi CDA (cuciture[basate su](field-based-stitching.md) campi e grafico [](device-graph.md)del dispositivo) calcolano il numero di persone univoche:

### Cuciture dal vivo

Non appena viene raccolto un hit, CDA tenta di incollarlo a dispositivi noti. Considerate l&#39;esempio seguente, in cui Bob utilizza due dispositivi.

*Dati visualizzati il giorno in cui viene raccolto:*

| Timestamp | ECID | eVar1 o CustomerID | Spiegazione dell&#39;hit | Metrica Persone (cumulativa) tramite Device Graph | Metrica Persone (cumulativa) con cuciture basate su campi |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sul suo computer desktop, non autenticato | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob accede al suo desktop | `1` (246) | `2` (246 e Bob) |
| `3` | `3579` | - | Bob sul suo dispositivo mobile, non autenticato | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `4` | `3579` | `Bob` | Bob effettua l’accesso sul dispositivo mobile | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `5` | `246` | - | Bob accede nuovamente al sito sul desktop, non autenticato | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `6` | `246` | `Bob` | Bob accede di nuovo tramite desktop | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `7` | `3579` | - | Bob accede di nuovo al sito su dispositivo mobile | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `8` | `3579` | `Bob` | Bob accede di nuovo tramite cellulare | `2` (246 e 3579) | `3` (246, Bob e 3579) |

Gli hit non autenticati e autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente).

* **Se si utilizza il grafico del dispositivo,** gli hit non autenticati sui dispositivi riconosciuti vengono cuciti in tempo reale una volta che un cluster viene pubblicato dal grafico del dispositivo. La pubblicazione dei cluster dura da tre ore a due settimane.

   Una terza persona cumulativa viene aggiunta anche quando viene pubblicato un cluster. Questa terza persona rappresenta il cluster stesso, oltre ai singoli dispositivi. Questa terza &quot;persona&quot; rimane finché non vengono riprodotti i dati.

   L&#39;attribuzione non funziona su più dispositivi fino a quando un cluster non viene pubblicato, e anche allora solo punti dal vivo da quel momento in poi. Nell’esempio precedente, nessuno degli hit è ancora incollato tra i dispositivi. L’attribuzione tra più dispositivi sugli hit esistenti non funziona fino a dopo la ripetizione dell’unione.
* **Se si utilizza la cucitura basata sul campo,** gli hit non autenticati sui dispositivi riconosciuti vengono cuciti in tempo reale da quel momento in poi.

   L&#39;attribuzione funziona non appena la variabile personalizzata di identificazione si collega a un dispositivo. Nell’esempio precedente, tutti gli hit tranne gli hit 1 e 3 sono live-cucite (usano tutti l’ `Bob` identificatore). L&#39;attribuzione funziona sugli hit 1 e 3 dopo la ripetizione dell&#39;unione dei punti.

### Ripetizione delle cuciture

Circa una volta alla settimana, CDA ricalcola i dati storici in base ai dispositivi che ora riconosce. Se un dispositivo invia inizialmente i dati non autenticati e quindi effettua l’accesso, CDA associa tali hit non autenticati alla persona corretta. La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla riproduzione dei dati.

*Gli stessi dati dopo la riproduzione:*

| Timestamp | ECID | eVar1 o CustomerID | Spiegazione dell&#39;hit | Metrica Persone (cumulativa) tramite Device Graph | Metrica Persone (cumulativa) con cuciture basate su campi |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob sul suo computer desktop, non autenticato | `1` (Cluster1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob accede al suo desktop | `1` (Cluster1) | `1` (Bob) |
| `3` | `3579` | - | Bob sul suo dispositivo mobile, non autenticato | `1` (Cluster1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob effettua l’accesso sul dispositivo mobile | `1` (Cluster1) | `1` (Bob) |
| `5` | `246` | - | Bob accede nuovamente al sito sul desktop, non autenticato | `1` (Cluster1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob accede di nuovo tramite desktop | `1` (Cluster1) | `1` (Bob) |
| `7` | `3579` | - | Bob accede di nuovo al sito su dispositivo mobile | `1` (Cluster1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob accede di nuovo tramite cellulare | `1` (Cluster1) | `1` (Bob) |

## Recap

* **Se si utilizza Device Graph,** i dati vengono cuciti quando un cluster viene pubblicato (in genere da 3 a 2 settimane).
* **Se si utilizza la cucitura basata su campo,** i dati di meno di una settimana vengono immediatamente cuciti sui dispositivi noti, ma non vengono immediatamente cuciti sui dispositivi nuovi o non riconosciuti.
* I dati vengono riprodotti una volta alla settimana e i dati storici nella suite di rapporti virtuali vengono modificati in base ai dispositivi che ha imparato a identificare.
