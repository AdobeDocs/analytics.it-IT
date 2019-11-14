---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# browserHeight

La variabile visualizza l'altezza della finestra del browser.

<!-- 
browserheight.xml
-->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

> [!NOTE] Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

**Parametri**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Query Param </th> 
   <th class="entry"> Valore </th> 
   <th class="entry"> Esempio  </th> 
   <th class="entry"> Report interessati </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>Un numero intero positivo </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Traffico &gt; Tecnologia &gt; Altezza browser </p> </td> 
  </tr> 
 </tbody> 
</table>

