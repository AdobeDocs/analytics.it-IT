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


# pageType

La variabile viene utilizzata solo per designare una pagina di errore 404 Pagina non trovata.

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 20 byte </td> 
   <td> pageType </td> 
   <td> Percorsi &gt; Pagine &gt; Pagine <p>Non trovato </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

La *`pageType`* variabile acquisisce l'URL errante quando viene visualizzata una pagina di errore 404, che consente di trovare rapidamente collegamenti interrotti e percorsi non più validi sul sito personalizzato. Impostare la *`pageType`* variabile sulla pagina di errore esattamente come illustrato di seguito.

Non utilizzate la variabile del nome della pagina su 404 pagine di errore. La *`pageType`* variabile viene utilizzata solo per la pagina Errore 404.

Nella maggior parte dei casi, la pagina 404 Error (Errore 404) è una pagina statica codificata. In questi casi, è importante che il riferimento al file JS sia impostato su un percorso/directory globale o relativo appropriato.

**Sintassi e valori** possibili {#section_C1C59968226446559B05F6EE7374D525}

L'unico valore consentito di *`pageType`* è "errorPage" come mostrato di seguito.

```js
s.pageType="errorPage"
```

**Esempi** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Impostazioni** di configurazione {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

Nessuno

**Insidie, domande e suggerimenti**{#section_943681AB01FE47BEAC72E93CB60C53C8}

Per acquisire altri errori sul lato server (ad esempio 500 errori), utilizzate una prop per acquisire il messaggio di errore e inserite "`500 Error: <URL>`" dove `<URL>` è l'URL richiesto nella *`pageName`* variabile. Seguendo questo corso di azione, puoi utilizzare [!UICONTROL Pathing] i rapporti per vedere quali percorsi hanno causato 500 errori agli utenti. Il prop spiega quale messaggio di errore viene fornito dal server.

