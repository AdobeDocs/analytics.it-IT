---
title: Confrontare i metodi di implementazione
description: Scopri i vantaggi di ciascun metodo che invia dati ad Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: c476a1a19ae514f75fce8bd8e6d447d85de67a84
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 5%

---

# Confrontare i metodi di implementazione

Scopri i diversi metodi di implementazione di Adobe Analytics. Puoi utilizzare queste tabelle per aiutare la tua organizzazione a determinare il modo più ideale per inviare dati ad Adobe. Fai clic su ciascuna colonna per informazioni più specifiche.

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Estensione Adobe Analytics](/help/implement/launch/overview.md) | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Estensione Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| Requisiti di implementazione | Fai riferimento a `AppMeasurement.js` in ogni pagina, definisci le variabili, invia dati tramite `s.t()` ad Adobe Analytics | Per fare riferimento al caricatore di tag in ogni pagina, utilizza l’interfaccia utente di Data Collection per definire le variabili e inviare i dati ad Adobe Analytics | Fai riferimento a `Alloy.js` in ogni pagina, utilizza `alloy("sendEvent",{})` per comporre oggetti XDM e inviare i dati desiderati utilizzando Edge Network ad Adobe Analytics | Fai riferimento al caricatore di tag in ogni pagina, utilizza l’interfaccia utente di Data Collection per comporre oggetti XDM e inviare i dati desiderati utilizzando l’Edge Network ad Adobe Analytics |
| Destinazione dati | Inviato direttamente ad Adobe Analytics | Inviato direttamente ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics |
| Difficoltà ad apportare modifiche all’implementazione | Richiede l’accesso al codice del sito web per ogni modifica dell’implementazione | Modifica il codice del sito web una volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente di Data Collection | Richiede l’accesso al codice del sito web per ogni modifica dell’implementazione | Modifica il codice del sito web una volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente di Data Collection |
| Come viene gestito A4T | Le chiamate A4T sono incluse negli hit inviati a Adobe | Le chiamate A4T sono incluse negli hit inviati a Adobe | Le chiamate A4T vengono inviate come hit separati | Le chiamate A4T vengono inviate come hit separati |
| Dati contestuali | Usa `s.contextData`. | Usa `s.contextData` nei blocchi di codice personalizzati | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. |

{style="table-layout:auto"}

## Mobile e altri

>[!CAUTION]
>
>Il supporto per gli SDK della versione 4 per dispositivi mobili è terminato il 31 agosto 2021. Per ulteriori informazioni, consulta [Domande frequenti sulla fine del ciclo di vita di Adobe Mobile Services](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=it).


| | [SDK per dispositivi mobili](/help/implement/aep-edge/mobile-sdk/overview.md) | [API server](/help/implement/aep-edge/server-api/overview.md) |
| --- | --- | --- |
| Requisiti di implementazione | Fai riferimento al caricatore di tag nell’app, quindi utilizza chiamate API dirette o regole nell’interfaccia utente di Data Collection per comporre oggetti XDM e inviare i dati desiderati utilizzando il codice di Edge Network ad Adobe Analytics | Utilizza Edge Network Server API per comporre oggetti XDM e inviare i dati desiderati utilizzando Edge Network ad Adobe Analytics |
| Destinazione dati | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics |
| Difficoltà ad apportare modifiche all’implementazione | Modifica il codice dell’app in cui vengono effettuate chiamate API dirette o apporta modifiche nell’interfaccia utente di Data Collection | Richiede l’accesso al codice dell’app per ogni modifica all’implementazione |
| Come viene gestito A4T | Le chiamate A4T vengono inviate come hit separati | Le chiamate A4T vengono inviate come hit separati |
| Dati contestuali | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto |

{style="table-layout:auto"}
