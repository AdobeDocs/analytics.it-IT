---
title: Confrontare i metodi di implementazione
description: Scopri i vantaggi di ciascun metodo che invia dati ad Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/Tx3YIRJv4Qztv-Bsa9XJFMFVE0PW9SnvgrYeMmrULiA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 500
ht-degree: 6%

---

# Confrontare i metodi di implementazione

Scopri i diversi metodi di implementazione di Adobe Analytics. Puoi utilizzare queste tabelle per aiutare la tua organizzazione a determinare il modo migliore per inviare dati ad Adobe. Fai clic su ciascuna colonna per informazioni più specifiche.

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Estensione Adobe Analytics](/help/implement/launch/overview.md) | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Estensione Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| Requisiti di implementazione | Fai riferimento a `AppMeasurement.js` in ogni pagina, definisci le variabili, invia dati tramite `s.t()` ad Adobe Analytics | Per fare riferimento al caricatore di tag in ogni pagina, utilizza l’interfaccia utente di Data Collection per definire le variabili e inviare i dati ad Adobe Analytics | Fai riferimento a `Alloy.js` in ogni pagina, utilizza `alloy("sendEvent",{})` per comporre oggetti XDM e inviare i dati desiderati tramite Edge Network ad Adobe Analytics | Per fare riferimento al caricatore di tag in ogni pagina, utilizza l’interfaccia utente di Data Collection per comporre oggetti XDM e inviare i dati desiderati tramite Edge Network ad Adobe Analytics |
| Destinazione dati | Inviato direttamente ad Adobe Analytics | Inviato direttamente ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics |
| Difficoltà ad apportare modifiche all’implementazione | Richiede l’accesso al codice del sito web per ogni modifica dell’implementazione | Modifica il codice del sito web una volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente di Data Collection | Richiede l’accesso al codice del sito web per ogni modifica dell’implementazione | Modifica il codice del sito web una volta per installare il tag loader; tutti gli ulteriori aggiornamenti dell’implementazione possono essere effettuati nell’interfaccia utente di Data Collection |
| Come viene gestito A4T | Le chiamate A4T sono incluse negli hit inviati ad Adobe | Le chiamate A4T sono incluse negli hit inviati ad Adobe | Le chiamate A4T vengono inviate come hit separati | Le chiamate A4T vengono inviate come hit separati |
| Dati contestuali | Usa `s.contextData`. | Usa `s.contextData` nei blocchi di codice personalizzati | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. |

{style="table-layout:auto"}

## Mobile e altri

>[!CAUTION]
>
>Il supporto per gli SDK della versione 4 per dispositivi mobili è terminato il 31 agosto 2021. Per ulteriori informazioni, consulta [Domande frequenti sulla fine del ciclo di vita di Adobe Mobile Services](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=it).


| | [Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md) | [API Edge Network](/help/implement/aep-edge/api/overview.md) |
| --- | --- | --- |
| Requisiti di implementazione | Fai riferimento al caricatore di tag nell’app, quindi utilizza chiamate API dirette o regole nell’interfaccia utente di Data Collection per comporre oggetti XDM e inviare i dati desiderati tramite Edge Network ad Adobe Analytics | Utilizza l’API di Edge Network per comporre oggetti XDM e inviare i dati desiderati tramite Edge Network ad Adobe Analytics |
| Destinazione dati | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics | Inviato ad Adobe Experience Platform Edge, che inoltra i dati ad Adobe Analytics |
| Difficoltà ad apportare modifiche all’implementazione | Modifica il codice dell’app in cui vengono effettuate chiamate API dirette o apporta modifiche nell’interfaccia utente di Data Collection | Richiede l’accesso al codice dell’app per ogni modifica all’implementazione |
| Come viene gestito A4T | Le chiamate A4T vengono inviate come hit separati | Le chiamate A4T vengono inviate come hit separati |
| Dati contestuali | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto. | Tutti i campi non mappati vengono inviati automaticamente come `a.x.*` variabili di dati di contesto |

{style="table-layout:auto"}
