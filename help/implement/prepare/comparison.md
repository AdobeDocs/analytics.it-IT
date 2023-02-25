---
title: Confronto dei metodi di implementazione
description: Scopri i vantaggi di ogni metodo che invia dati ad Adobe Analytics.
source-git-commit: 2e69321404237213c6929f3fb0c330575d8a90db
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 4%

---

# Confronto dei metodi di implementazione

Scopri in che modo ogni metodo di implementazione di Adobe Analytics si confronta. Puoi utilizzare questa tabella per aiutare la tua organizzazione a determinare il modo più ideale per inviare dati ad Adobe.

|  | AppMeasurement | Estensione Adobe Analytics | SDK per web | Estensione SDK per web |
| --- | --- | --- | --- | --- |
| Requisiti di implementazione | Riferimento `AppMeasurement.js` su ogni pagina, definisci variabili, invia dati utilizzando `s.t()` | Caricatore di tag di riferimento su ogni pagina, utilizza l’interfaccia utente di raccolta dati per definire le variabili e inviare i dati ad Adobe | Riferimento `Alloy.js` in ogni pagina, utilizza `alloy("sendEvent",{})` per inviare un oggetto JSON contenente i dati desiderati | Caricatore di tag di riferimento su ogni pagina, utilizza l’interfaccia utente di raccolta dati per stabilire l’oggetto JSON da inviare ai dati |
| Destinazione dati | Inviato direttamente ad Adobe Analytics | Inviato direttamente ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics |
| Difficoltà nell’apportare modifiche all’implementazione | Richiede l&#39;accesso al codice del sito web per ogni modifica di implementazione | Modificare il codice del sito web una volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente Raccolta dati | Richiede l&#39;accesso al codice del sito web per ogni modifica di implementazione | Modificare il codice del sito web una volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente Raccolta dati |
| Gestione di A4T | Le chiamate A4T sono incluse negli hit inviati ad Adobe | Le chiamate A4T sono incluse negli hit inviati ad Adobe | Le chiamate A4T vengono inviate come hit separati | Le chiamate A4T vengono inviate come hit separati |
| Dati contestuali | Seleziona `s.contextData`. | Utilizzo `s.contextData` nei blocchi di codice personalizzati | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. |

{style=&quot;table-layout:auto&quot;}
