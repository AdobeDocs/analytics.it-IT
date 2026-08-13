---
title: Panoramica sui plug-in
description: Incolla il codice sul tuo sito per introdurre nuove funzionalità.
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ImzoBRU0DajPc99vRlu1698CteFNk9dOS2OZrN9DBZs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 9%

---

# Panoramica sui plug-in

I plug-in sono snippet di codice che eseguono diverse funzioni avanzate per facilitare l’implementazione di Analytics. Questi plug-in estendono le funzionalità del file JavaScript per offrire ulteriori funzionalità non disponibili con un’implementazione di base. Adobe offre una serie di altri plug-in come parte delle soluzioni avanzate.

{{plug-in}}

Adobe offre diversi modi per installare un determinato plug-in:

* Utilizzare l’estensione &quot;Common Analytics Plugins&quot; tramite l’estensione Adobe Analytics
* Incollare il codice del plug-in utilizzando l’editor di codice personalizzato
* Incolla il codice del plug-in nel file `AppMeasurement.js`

Ogni organizzazione ha esigenze di implementazione diverse, per cui puoi decidere come includerle nell’implementazione. Assicurati di soddisfare i seguenti criteri quando includi il codice sul sito:

1. Creare prima un&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)).
   * Il sito abilitato ai tag crea automaticamente un’istanza dell’oggetto di tracciamento al caricamento di Adobe Analytics.
   * Le implementazioni che utilizzano `AppMeasurement.js` in genere inizializzano l&#39;oggetto di tracciamento nella parte superiore del file JavaScript.
2. Includi codice plug-in al secondo.
   * L’estensione Common Analytics Plugins dispone di una configurazione delle azioni in cui è possibile inizializzare i plug-in.
   * Se non desideri utilizzare l’estensione, puoi incollare il codice del plug-in nell’editor di codice personalizzato durante la configurazione dell’estensione Analytics.
   * Se l&#39;implementazione non utilizza i tag in Adobe Experience Platform, puoi incollare il codice del plug-in in `AppMeasurement.js` in qualsiasi punto dopo aver creato un&#39;istanza dell&#39;oggetto di tracciamento.
3. Chiamare il terzo plug-in.
   * Tutte le implementazioni, sia all’interno che all’esterno di un sito abilitato ai tag, utilizzano JavaScript per chiamare i plug-in. Chiamare il plug-in utilizzando il formato documentato nella pagina del plug-in.
4. Convalida l’implementazione e pubblica.

Molte organizzazioni chiamano i plug-in utilizzando la funzione [`doPlugins`](../functions/doplugins.md). Anche se questa funzione non è richiesta, Adobe la considera una best practice da utilizzare. AppMeasurement richiama questa funzione subito prima di compilare e inviare una richiesta di immagine, il che è ideale poiché diversi plug-in dipendono da altre variabili di Analytics.

## Plug-in ritirati

I seguenti plug-in vengono ritirati. Sono documentati qui come riferimento se si trovano in un’implementazione legacy.

* **`getPageLoadTime`**: misurato il tempo necessario al caricamento completo di una pagina utilizzando l&#39;oggetto prestazioni di JavaScript. Non è più supportato perché il suo codice si basa sull&#39;interfaccia [`PerformanceTiming`](https://developer.mozilla.org/it-IT/docs/Web/API/PerformanceTiming), che è obsoleta nella maggior parte dei browser moderni. Non è prevista la sostituzione diretta e le istruzioni di installazione e il codice del plug-in non sono più disponibili.
