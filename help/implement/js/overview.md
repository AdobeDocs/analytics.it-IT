---
title: AppMeasurement per JavaScript
description: Scoprite come implementare  Adobe Analytics utilizzando JavaScript senza un sistema di gestione dei tag.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 4%

---


# AppMeasurement per JavaScript

AppMeasurement per JavaScript è stato storicamente un metodo comune per implementare  Adobe Analytics. Tuttavia, con la crescente popolarità dei sistemi di gestione dei tag, è consigliabile utilizzare [Adobe Experience Platform Launch](../launch/overview.md) .

## Flusso di lavoro complessivo per l&#39;invio di dati a  Adobe tramite JavaScript

1. Caricate il `AppMeasurement.js` file. Questo file contiene le librerie necessarie per inviare i dati a  Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Definite le variabili di configurazione all&#39;interno `AppMeasurement.js`. Quando viene creata un&#39;istanza dell&#39;oggetto Analytics, queste variabili assicurano che le impostazioni di raccolta dati siano corrette. Consulta Variabili [di](../vars/config-vars/configuration-variables.md) configurazione per un elenco completo delle variabili che puoi definire.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. Definite le variabili a livello di pagina nel codice della pagina del sito. Queste variabili determinano specifiche dimensioni e metriche inviate al Adobe . Consulta Variabili [di](../vars/page-vars/page-variables.md) pagina per un elenco completo delle variabili che puoi definire.

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. Quando tutte le variabili a livello di pagina sono definite, inviate i dati a  Adobe utilizzando il `t()` metodo . Per [ulteriori informazioni, consulta](../vars/functions/t-method.md) .

   ```js
   s.t();
   ```
