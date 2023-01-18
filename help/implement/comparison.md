---
title: Confronto dei metodi di implementazione
description: Scopri i vantaggi di ogni metodo che invia dati ad Adobe Analytics.
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# Confronto dei metodi di implementazione

Scopri in che modo ogni metodo di implementazione di Adobe Analytics si confronta. Puoi utilizzare questa tabella per aiutare la tua organizzazione a determinare il modo più ideale per inviare dati ad Adobe.

|  | AppMeasurement | Estensione Adobe Analytics | SDK per web | Estensione SDK per web |
| --- | --- | --- | --- | --- |
| Requisiti di implementazione | Riferimento `AppMeasurement.js` su ogni pagina, definisci variabili, invia dati utilizzando `s.t()` | Caricatore di tag di riferimento su ogni pagina, utilizza l’interfaccia utente di raccolta dati per definire le variabili e inviare i dati ad Adobe | Riferimento `Alloy.js` in ogni pagina, utilizza `alloy("sendEvent",{})` per inviare un oggetto JSON contenente i dati desiderati | Caricatore di tag di riferimento su ogni pagina, utilizza l’interfaccia utente di raccolta dati per stabilire l’oggetto JSON da inviare ai dati |
| Destinazione dati | Inviato direttamente ad Adobe Analytics | Inviato direttamente ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics |
| Difficoltà nell’apportare modifiche all’implementazione | Richiede l&#39;accesso al codice del sito web per ogni modifica di implementazione | Il codice del sito web deve essere modificato una sola volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente Raccolta dati | Richiede l&#39;accesso al codice del sito web per ogni modifica di implementazione | Il codice del sito web deve essere modificato una sola volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente Raccolta dati |
| Gestione di A4T | Le chiamate A4T sono incluse negli hit inviati ad Adobe | Le chiamate A4T sono incluse negli hit inviati ad Adobe | Le chiamate A4T vengono inviate come hit separati | Le chiamate A4T vengono inviate come hit separati |
| Gestione del referente |