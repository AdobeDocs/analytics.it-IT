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


# Variabile elenco

Noto anche come Var elenco. Analogamente alla funzione Elenco proprietà, le Var elenco consentono più valori all’interno della stessa richiesta di immagine. Inoltre, agiscono in modo simile alle eVar, che persistono oltre la richiesta di immagine sulla quale sono state definite. Potete utilizzare queste variabili per visualizzare la causa e l'effetto tra più elementi su una singola pagina, come elenchi di prodotti, elenchi di desideri, elenchi di miglioramenti della ricerca o elenchi di annunci visualizzati.

<!-- 

listN.xml

 -->

**Considerazioni**

* Le variabili elenco ricordano i loro valori specifici facendo riferimento al cookie VisitorID nel browser del visitatore.
* Un limite massimo di 250 valori viene memorizzato alla volta per visitatore. Se vengono superati i 250 valori per visitatore, vengono usati gli ultimi 250 valori. La scadenza di tali valori si basa sulla scadenza configurata per la variabile.
* Ogni valore delimitato può contenere un massimo di 255 caratteri (o meno se si utilizzano caratteri multibyte). Questa è la lunghezza massima di ogni elemento.
* Non esiste alcun limite al numero di caratteri all'interno di questa variabile. L’unica eccezione a questa limitazione è rappresentata dai browser Internet Explorer meno recenti, che impongono un limite di 2083 caratteri per tutte le richieste URL.
* Per suite di rapporti sono disponibili in totale tre variabili elenco.
* L'utilizzo di List Vars richiede il codice H23 o superiore.
* Le variabili elenco possono essere classificate.
* Se i valori duplicati sono definiti nella stessa richiesta di immagine, le variabili elenco deduplicano tutte le istanze di tali valori.
* Le variabili di elenco più granulari possono essere segmentate a livello di hit (o visualizzazione pagina). Se nella stessa richiesta di immagine è presente una variabile di elenco con tre valori, tutte e tre le regole di segmento che corrispondono a un valore verranno sottoposte a reporting. Al contrario, se viene definita una regola di esclusione che corrisponde a un singolo valore, vengono esclusi tutti e tre i valori.

**Configurazione** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

Puoi accedere alla configurazione in Admin Console e aggiornarla senza dover coinvolgere Adobe Client Care:

1. Vai a  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**
1. Seleziona la suite di rapporti.
1. Clic  **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

* **Nome**:Ogni valore delimitato può contenere un massimo di 255 caratteri (o meno se si utilizzano caratteri multibyte). Questa è la lunghezza massima di ogni elemento.
* **Delimitatore** valore: Il carattere utilizzato per separare i valori all'interno della Var elenco. Nella maggior parte dei casi, si tratta di caratteri quali virgole, due punti, una tubatura o qualcosa di simile.

   >[!NOTE]
   >
   >I caratteri multibyte non sono supportati come delimitatori nelle variabili di elenco. Il delimitatore deve essere a byte singolo.

* **Scadenza**: Simile alla scadenza dell'eVar, questo determina la quantità di tempo che può trascorrere tra la Var dell'elenco e l'evento di conversione per il relativo collegamento.

   * **A un livello** di visualizzazione pagina o visita: Gli eventi di successo oltre la visualizzazione della pagina o la visita non verrebbero collegati ad alcun valore all’interno della Var elenco.
   * **In base a un periodo di tempo, ad esempio giorno, settimana, mese, ecc**.: Gli eventi di successo oltre il periodo di tempo specificato non verranno collegati ai valori all'interno della Var elenco. È inoltre possibile definire un numero personalizzato di giorni.
   * **Eventi** di conversione specifici: Eventuali altri eventi di successo attivati dopo lo specifico evento designato non verranno collegati ai valori all'interno della Var elenco.
   * **Mai**: Qualsiasi quantità di tempo può passare tra la Var elenco e l'evento success.

* **Allocazione**: Questa impostazione determina in che modo gli eventi di successo dividono il credito tra i valori:

   * **Completa**: Tutti i valori delle variabili definiti prima della scadenza della variabile ottengono il credito completo per gli eventi di successo.
   * **Lineare**: Tutti i valori delle variabili definiti prima della scadenza della variabile ricevono credito diviso per gli eventi di conversione.
   * I valori delle variabili non vengono mai sovrascritti, ma vengono aggiunti ai valori che vengono accreditati per gli eventi di successo.

* **Valori** max: Indica il numero di valori attivi consentiti per questa variabile dell'elenco. Ad esempio, se è impostato su 3, vengono salvati solo gli ultimi 3 valori acquisiti e tutti i valori acquisiti in precedenza vengono scartati. Tenere presente che se più valori per lo stesso elenco var vengono inviati nello stesso hit e avete applicato delle restrizioni utilizzando i valori massimi, ogni valore avrà la stessa marca temporale e non vi è alcuna garanzia per quale valore viene salvato.

   Un limite massimo di 250 valori viene memorizzato alla volta per visitatore. Se vengono superati i 250 valori per visitatore, vengono usati gli ultimi 250 valori. La scadenza di tali valori si basa sulla scadenza configurata per la variabile.

   L’impostazione Valori massimi è utile per limitare l’attribuzione a un numero specifico di valori. Ad esempio, se una variabile di elenco è impostata su "A,B,C" nella prima pagina di una visita e quindi su "X,Y,Z" nella pagina successiva, l'attribuzione viene distribuita a questi sei valori in base all'allocazione. Se desiderate limitare l’attribuzione solo a "X,Y,Z", potete impostare i valori massimi su tre.

Per impostare o modificare le Var elenco, scegliere **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

**Esempi** di implementazione {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

Per ciascuno degli esempi seguenti viene utilizzata una virgola come delimitatore di valori.

**Definizione di un singolo valore all'interno di una Var elenco:**

```js
s.list1="Cat";
```

**Trasmissione di più valori:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Attribuzione delle entrate a una variabile di elenco:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

Questo risultato mostrerebbe tre voci con $50 ciascuna in entrate. (Annuncio banner superiore; Annuncio barra laterale; e campagna interna 1.) Il totale per questo rapporto deduplica le entrate, pertanto il totale riflette anche $50.

**Attribuzione delle entrate a una Var elenco impostata più volte durante una visita:**

**Allocazione**: Full

**Scadenza**: Visita

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Pagina 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (non impostato) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pagina 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Risultato**: Tutti i valori impostati nell'elenco var1 in qualsiasi punto della visita (valore1,valore2,valore3,valore4,valore5,valore6) ottengono il credito completo per l'acquisto.

