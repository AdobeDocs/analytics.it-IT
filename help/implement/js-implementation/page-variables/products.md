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


# products

La variabile viene utilizzata per tenere traccia dei prodotti e delle categorie di prodotti, nonché della quantità di acquisto e del prezzo di acquisto. I prodotti vengono generalmente impostati insieme a un evento cart o un evento.

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. Questo aggiornamento può causare l'aumento degli *eventi`prodView`* *`prodViews`* aumenteranno solo nei casi in cui:
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
   >
   >
1. The *`products`* variable is not empty.
>
>
A possible side effect is that merchandising eVars triggered by *`prodView`* events could be associated with an empty *`product`*, but only if the *`product list`* contains only an invalid product (such as a semicolon with no product listed).

La *`products`* variabile tiene traccia di come gli utenti interagiscono con i prodotti sul sito. Ad esempio, la variabile "products" può tenere traccia del numero di volte in cui un prodotto viene visualizzato, aggiunto al carrello, estratto e acquistato. Può inoltre tenere traccia dell’efficacia relativa delle categorie di merchandising sul sito. Gli scenari riportati di seguito sono comuni per l'utilizzo della variabile "products".

La *`products`* variabile deve sempre essere impostata insieme a un evento success.

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
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
   <td> <p>La stringa " <span class="wintitle"> products </span>" ha una dimensione massima di 64 k. </p> </td> 
   <td> products </td> 
   <td> Prodotti <p>Categorie (facoltativo) </p> <p>Entrate (facoltativo) </p> <p>Unità (facoltativo) </p> <p>Eventi personalizzati (facoltativo) </p> <p>eVar (facoltativo) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Sintassi** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| Campo | Definizione |
|---|---|
| Categoria | Contiene la categoria di prodotti associata. Nella versione 15, i prodotti possono essere associati a più categorie, il che risolve una limitazione presente nella versione 14. Se in precedenza non si registrava una categoria di prodotti, si consiglia di iniziare a compilare il campo per le suite di rapporti che si trovano sulla versione 15. |
| Prodotto | (Obbligatorio) Identificatore utilizzato per tenere traccia di un prodotto. Questo identificatore viene utilizzato per compilare il [!UICONTROL Products] rapporto. Assicuratevi di utilizzare lo stesso identificatore attraverso il processo di estrazione. |
| Quantità | Numero di unità acquistate. Questo campo deve essere impostato con un [!UICONTROL purchase] evento da registrare. |
| Prezzo | Si riferisce al costo combinato della quantità totale acquistata (unità x prezzo unitario singolo), non al prezzo individuale. Questo campo deve essere impostato con un [!UICONTROL purchase] evento da registrare. |
| Eventi | Eventi valuta associati al prodotto specificato. Vedere Eventi [valuta specifici per](/help/implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C) il prodotto ed Eventi [valuta a livello di](/help/implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0)ordine. |
| eVar | Valore eVar di merchandising associato a un prodotto specifico. Consultate Variabili [di](/help/components/c-variables/c-merch-variables/var-merchandising.md)merchandising. |

I valori inclusi nella *`products`* variabile si basano sul tipo di evento che si sta registrando. Il delimitatore di categoria/prodotto (;) è richiesto come segnaposto quando si omette Categoria. Altri delimitatori sono richiesti solo se sono necessari per distinguere il parametro da includere, come mostrato negli esempi in questa pagina.

**Impostazione di prodotti con eventi** non di acquisto {#section_D5E689D4AAE941EC851CA9B98328A4DE}

La *`products`* variabile deve essere impostata insieme a un evento success.

**Impostazione di prodotti con un evento** di acquisto {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

L' *`purchase`* evento deve essere impostato sulla conferma finale ("Grazie!") pagina del processo di ordine. Il nome del prodotto, la categoria, la quantità e il prezzo sono tutti acquisiti nella *`products`* variabile. Sebbene la *`purchaseID`* variabile non sia obbligatoria, è fortemente consigliata per evitare ordini duplicati.

**Eventi** valuta specifici per il prodotto {#section_F814DF053C0D463A97DA039E6323720C}

Se un evento relativo alla valuta riceve un valore nella variabile anziché nella variabile *`products`* event, esso si applica solo a tale valore. Questo è utile per monitorare gli sconti specifici per prodotto, la spedizione di prodotti e valori simili. Ad esempio, se hai configurato l'evento 1 per monitorare la spedizione del prodotto, un prodotto con una spesa di spedizione "4.50" potrebbe essere simile al seguente:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

In questo esempio, il valore 4.50 è associato direttamente al prodotto "Running Shoes". Se aggiungete event1 al rapporto sui prodotti, vedrete "4.50" elencato per la voce "Scarpe in esecuzione". Simile a Prezzo, questo valore deve riflettere il totale per la quantità indicata. Se avete 2 articoli con una spesa di spedizione di 4.50 ciascuno, event1 deve essere "9.00".

**Eventi** valuta a livello di ordine {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

Se un evento relativo alla valuta riceve un valore nell'elenco eventi anziché nella *`products`* variabile, questo viene applicato a tutti i prodotti della *`products`* variabile. Questo è utile per tenere traccia degli sconti, delle spedizioni e di valori simili a livello di ordine, senza modificare il prezzo del prodotto o registrarlo separatamente nell'elenco dei prodotti.

Ad esempio, se hai configurato event10 per contenere sconti a livello di ordine, un acquisto con uno sconto del 10% potrebbe essere simile al seguente:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

Nei rapporti evento valuta, il totale del rapporto rappresenta il totale degli eventi deduplicati (in questo esempio, l'importo totale degli sconti durante il periodo di reporting), non la somma dei valori evento per ciascun prodotto. Ad esempio, vedreste "9.95" sia per "Scarpe In Corsa" che per "Calzature In Corsa", e il totale sarebbe anche "9.95".

> [!NOTE] se un valore per lo stesso evento Numerico/Valuta è specificato nella *`products`* variabile e nella *`events`* variabile, viene utilizzato il valore del *`events`* .

**Insidie, domande e suggerimenti**{#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* La *`products`* variabile deve sempre essere impostata insieme a un [!UICONTROL success] evento (eventi). Se non viene [!UICONTROL success] specificato alcun evento, l'evento predefinito è [!UICONTROL prodView].

* Rimuovere tutte le virgole e i punti e virgola dai nomi di prodotti e categorie prima di compilare i prodotti.
* Rimuovete tutti i caratteri HTML (simboli registrati, marchi registrati e così via).
* Elimina simboli di valuta ($) dal prezzo.

**Esempi** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

