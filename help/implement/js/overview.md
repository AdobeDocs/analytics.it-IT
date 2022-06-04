---
title: Implementazione di Adobe Analytics con AppMeasurement per JavaScript
description: Scopri come implementare Adobe Analytics utilizzando JavaScript senza un sistema di gestione dei tag.
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
source-git-commit: 99fc7814eaa12d0d9e8e478629a4c2134a577aaa
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 0%

---

# Implementazione di Adobe Analytics con AppMeasurement per JavaScript

AppMeasurement per JavaScript è stato storicamente un metodo comune per implementare Adobe Analytics. Tuttavia, con la crescente popolarità di Tag Management Systems, utilizzando [tag in Adobe Experience Platform](../launch/overview.md) è consigliato.

## Invio complessivo di dati ad Adobe tramite JavaScript

1. Carica il `AppMeasurement.js` file. Questo file contiene le librerie necessarie per inviare dati ad Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Definisci le variabili di configurazione in `AppMeasurement.js`. Quando viene creata un&#39;istanza dell&#39;oggetto Analytics, queste variabili si accertano che le impostazioni di raccolta dati siano corrette. Vedi [Variabili di configurazione](../vars/config-vars/configuration-variables.md) per un elenco completo delle variabili che puoi definire.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. Definisci le variabili a livello di pagina all&#39;interno del codice della pagina del sito. Queste variabili determinano la dimensione specifica e le metriche inviate ad Adobe. Vedi [Variabili di pagina](../vars/page-vars/page-variables.md) per un elenco completo delle variabili che puoi definire.

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. Quando sono definite tutte le variabili a livello di pagina, invia i dati ad Adobe utilizzando `t()` metodo . Vedi [t](../vars/functions/t-method.md) per ulteriori informazioni.

   ```js
   s.t();
   ```
