---
title: AppMeasurement per JavaScript
description: Scopri come implementare Adobe Analytics utilizzando JavaScript senza un sistema di gestione dei tag.
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 4%

---

# AppMeasurement per JavaScript

AppMeasurement per JavaScript è stato storicamente un metodo comune per implementare Adobe Analytics. Tuttavia, con l&#39;aumento della popolarità dei sistemi di gestione dei tag, si consiglia di utilizzare i tag [in Adobe Experience Platform](../launch/overview.md).

## Invio complessivo di dati ad Adobe tramite JavaScript

1. Carica il file `AppMeasurement.js`. Questo file contiene le librerie necessarie per inviare dati ad Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Definisci le variabili di configurazione in `AppMeasurement.js`. Quando viene creata un&#39;istanza dell&#39;oggetto Analytics, queste variabili si accertano che le impostazioni di raccolta dati siano corrette. Consulta [Variabili di configurazione](../vars/config-vars/configuration-variables.md) per un elenco completo delle variabili che puoi definire.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. Definisci le variabili a livello di pagina all&#39;interno del codice della pagina del sito. Queste variabili determinano la dimensione specifica e le metriche inviate ad Adobe. Consulta [Variabili di pagina](../vars/page-vars/page-variables.md) per un elenco completo delle variabili che puoi definire.

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. Quando sono definite tutte le variabili a livello di pagina, invia i dati ad Adobe utilizzando il metodo `t()` . Per ulteriori informazioni, consulta [t](../vars/functions/t-method.md) .

   ```js
   s.t();
   ```
