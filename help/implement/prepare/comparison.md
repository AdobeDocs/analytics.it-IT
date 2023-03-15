---
title: Confrontare i metodi di implementazione
description: Scopri i vantaggi di ciascun metodo che invia dati ad Adobe Analytics.
source-git-commit: 2e69321404237213c6929f3fb0c330575d8a90db
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 3%

---

# Confrontare i metodi di implementazione

Scopri i diversi metodi di implementazione di Adobe Analytics. Puoi utilizzare questa tabella per aiutare la tua organizzazione a determinare il modo più ideale per inviare dati ad Adobe.

|  | AppMeasurement | Estensione Adobe Analytics | SDK per web | Estensione Web SDK |
| --- | --- | --- | --- | --- |
| Requisiti di implementazione | Riferimento `AppMeasurement.js` in ogni pagina, definisci le variabili e invia i dati utilizzando `s.t()` | Per fare riferimento al caricatore di tag in ogni pagina, utilizza l’interfaccia utente di Data Collection per definire le variabili e inviare i dati agli Adobi. | Riferimento `Alloy.js` in ogni pagina, utilizza `alloy("sendEvent",{})` per inviare un oggetto JSON contenente i dati desiderati | Per fare riferimento al caricatore di tag in ogni pagina, utilizza l’interfaccia utente di Data Collection per stabilire l’oggetto JSON da inviare ai dati |
| Destinazione dati | Inviato direttamente ad Adobe Analytics | Inviato direttamente ad Adobe Analytics | Inviato a Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics | Inviato a Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics |
| Difficoltà ad apportare modifiche all’implementazione | Richiede l’accesso al codice del sito web per ogni modifica dell’implementazione | Modifica il codice del sito web una volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente di Data Collection | Richiede l’accesso al codice del sito web per ogni modifica dell’implementazione | Modifica il codice del sito web una volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente di Data Collection |
| Come viene gestito A4T | Le chiamate A4T sono incluse negli hit inviati a Adobe | Le chiamate A4T sono incluse negli hit inviati a Adobe | Le chiamate A4T vengono inviate come hit separati | Le chiamate A4T vengono inviate come hit separati |
| Dati contestuali | Seleziona `s.contextData`. | Utilizzare `s.contextData` nei blocchi di codice personalizzato | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. |

{style="table-layout:auto"}
