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



# browserWidth

La variabile visualizza la larghezza della finestra del browser.

<!-- 

browserwidth.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

> [!NOTE] Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

**Parametri**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Query Param</b> </p> </td> 
   <td> <p> <b>Valore</b> </p> </td> 
   <td> <p> <b>Esempio</b> </p> </td> 
   <td> <p> <b>Report interessati</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>Un numero intero positivo </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Traffico &gt; Tecnologia &gt; Larghezza browser </p> </td> 
  </tr> 
 </tbody> 
</table>
