---
description: Selezionando l'icona a forma di ingranaggio accanto a una metrica è possibile specificare il tipo di metrica e il modello di attribuzione.
seo-description: Selezionando l'icona a forma di ingranaggio accanto a una metrica è possibile specificare il tipo di metrica e il modello di attribuzione.
seo-title: Tipo di metrica e attribuzione
title: Tipo di metrica e attribuzione
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Tipo di metrica e attribuzione

Selezionando l'icona a forma di ingranaggio accanto a una metrica è possibile specificare il tipo di metrica e il modello di attribuzione.

* [Tipi di metriche](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [Modello di attribuzione colonna](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [Come funziona l'allocazione lineare (dal 19 luglio 2018)](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## Tipi di metriche {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| Tipi di metriche | Definizione |
|---|---|
| Standard | Queste metriche sono le stesse utilizzate per il [!DNL Analytics] reporting standard. Se una formula è costituita da una singola metrica standard, vengono visualizzati dati identici alla controparte non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singolo elemento riga. Ad esempio, [Ordini] / [Visite] riceve gli ordini per quell'articolo specifico e lo divide per il numero di visite per quell'articolo specifico. |
| Totale | Utilizzare il totale per il periodo di reporting in ogni voce di riga. Se una formula è costituita da una singola metrica totale, visualizza lo stesso numero totale su ogni elemento riga. Le metriche totali sono utili per creare metriche calcolate confrontate con i dati totali del sito. Ad esempio, [Ordini] / Visite [] totali mostra la proporzione di ordini rispetto a TUTTE le visite al sito, non solo le visite all'elemento riga specifico. |

## Modello di attribuzione colonna {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>Nel luglio 2018, [!DNL Analytics] è stato introdotto [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), che ha modificato il modo in cui vengono valutati i modelli di allocazione nelle metriche calcolate. Come parte di questa modifica, le metriche calcolate che utilizzano un modello di allocazione non predefinito sono state migrate in nuovi modelli di attribuzione migliorati:
>
>* Per un elenco completo dei modelli di attribuzione e delle finestre di lookback non predefiniti supportati, consultate la documentazione di [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html) .
>* I modelli di allocazione "Marketing Channel Last Touch" e "Marketing Channel First Touch" verranno migrati rispettivamente ai nuovi modelli di attribuzione "Last Touch" e "First Touch" (Nota: "Marketing Channels" (Canali di marketing) non verrà dichiarato obsoleto; verranno visualizzati solo i due modelli di allocazione nelle metriche calcolate.
>* Inoltre, correggeremo il modo in cui viene calcolata l'allocazione lineare. Per i clienti che utilizzano metriche calcolate con modelli di allocazione "Lineare", i report potrebbero leggermente cambiare per riflettere il nuovo modello di attribuzione corretto. This change to calculated metrics will be reflected in Analysis Workspace, [!UICONTROL Reports & Analytics], the Reporting API, Report Builder, and Ad Hoc Analysis. Per ulteriori informazioni, vedere [Funzionamento dell'allocazione lineare (dal 19 luglio 2018)](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1).
>



## Come funziona l'allocazione lineare (dal 19 luglio 2018) {#section_EDBB2E14A6C248C5A79C0913C02D7CA1}

Nel luglio 2018, Adobe ha modificato il modo in cui viene riportata l'allocazione lineare per le metriche calcolate. Questa modifica interessa Analysis Workspace, Analisi ad hoc, [!UICONTROL Reports & Analytics], Generatore di report, Activity Map e le API di reporting. La modifica interesserà principalmente le eVar e altre dimensioni persistenti. Queste modifiche si applicano solo alle metriche calcolate e non avranno alcun impatto sugli altri report che utilizzano l'allocazione lineare (come il report Pagine in [!UICONTROL Reports & Analytics]). Altri rapporti che utilizzano l'allocazione lineare continueranno a utilizzare il metodo esistente di allocazione lineare.

L'esempio seguente illustra come le metriche calcolate con allocazione lineare cambieranno nei report:

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Hit 1 </th> 
   <th colname="col3" class="entry"> Hit 2 </th> 
   <th colname="col4" class="entry"> Hit 3 </th> 
   <th colname="col5" class="entry"> Hit 4 </th> 
   <th colname="col6" class="entry"> Hit 5 </th> 
   <th colname="col7" class="entry"> Hit 6 </th> 
   <th colname="col8" class="entry"> Hit 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dati inviati in </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ultima eVar tocco </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> PROMO B </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>First Touch eVar </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO A </td> 
   <td colname="col6"> PROMO A </td> 
   <td colname="col7"> PROMO A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esempio di proprietà </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

In questo esempio, i valori A, B e C sono stati inviati in una variabile sugli hit 1, 3, 4 e 6 prima che un acquisto di $10 fosse effettuato sull'hit 7. Nella seconda riga, questi valori persistono tra gli hit in base all’ultima visita di tocco. La terza riga illustra una persistenza della visita di primo tocco. Infine, l'ultima riga illustra come i dati verrebbero registrati per una prop che non ha persistenza.

**Riepilogo del funzionamento dell’allocazione lineare prima di luglio 2018**

Prima del 19 luglio 2018, l'attribuzione lineare è stata calcolata dopo che si è già verificata la persistenza del primo tocco o dell'ultimo tocco. Ciò significa che per l'ultima eVar touch sopra, i $10 sarebbero distribuiti come segue: A = 10 * (3/6) = $5, B = 10 * (2/6) = $3,33, C = 10 * (1/6) = $1,67.

Per la prima eVar touch sopra, tutti $10 sarebbe dato a A. Per il prop: A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50, e C = 10 * (1/4) = $2,50. Per riepilogare l'allocazione lineare come funzionava in precedenza:

| Valori | Ultima eVar di tocco corrente | Prima eVar touch corrente | Prop corrente |
|---|---|---|---|
| PROMO A | $ 5,00 | $10.00 | $ 5,00 |
| PROMO B | $3.33 | $0 | $ 2,50 |
| PROMO C | $1.67 | $0 | $ 2,50 |
| Totale | $10.00 | $10.00 | $10.00 |

**Riepilogo del funzionamento dell’allocazione lineare a partire dal 19 luglio 2018**

Dopo il 19 luglio, abbiamo corretto questo comportamento nelle metriche calcolate. Invece di utilizzare i valori persistenti basati sull'ultimo tocco o sul primo tocco, [!DNL Analytics] ora utilizza solo i valori passati (la prima riga della tabella superiore). Di conseguenza, le impostazioni di allocazione delle dimensioni non influiscono più sul modo in cui viene calcolata l'allocazione lineare (vale a dire proprietà e eVar saranno trattate allo stesso modo), e i risultati riflettono ciò che è stato originariamente passato al posto dei valori del primo o dell'ultimo tocco che potrebbero essere persistenti. Quindi, in tutti e tre i casi, A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50, e C = 10 * (1/4) = $2,50.

| Valori | Nuova eVar ultimo tocco | Nuova eVar Touch | Nuovo prop |
|---|---|---|---|
| PROMO A | $ 5,00 | $ 5,00 | $ 5,00 |
| PROMO B | $ 2,50 | $ 2,50 | $ 2,50 |
| PROMO C | $ 2,50 | $ 2,50 | $ 2,50 |
| Totale | $10.00 | $10.00 | $10.00 |

<!-- 

<p>Additionally, as part of this change, [!DNL Analytics] is <b>changing how multiple sequential successes</b> are treated. In the following example, 7 hits occurred in the same visit with two orders, one $10 order on hit 4, and one $5 order on hit 7: </p> 
<table id="table_4647AA466D1447F6961DDC10468FCCE1"> 
 <tgroup cols="8">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="1.04*" />
  <colspec colnum="3" colname="col3" colwidth="1.02*" />
  <colspec colnum="4" colname="col4" colwidth="1.02*" />
  <colspec colnum="5" colname="col5" colwidth="1.03*" />
  <colspec colnum="6" colname="col6" colwidth="1.02*" />
  <colspec colnum="7" colname="col7" colwidth="1.02*" />
  <colspec colnum="8" colname="col8" colwidth="1.03*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> </th> 
    <th colname="col2" class="entry"> Hit 1 </th> 
    <th colname="col3" class="entry"> Hit 2 </th> 
    <th colname="col4" class="entry"> Hit 3 </th> 
    <th colname="col5" class="entry"> Hit 4 </th> 
    <th colname="col6" class="entry"> Hit 5 </th> 
    <th colname="col7" class="entry"> Hit 6 </th> 
    <th colname="col8" class="entry"> Hit 7 </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Data Sent In </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Last Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO B </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>First Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO A </td> 
    <td colname="col7"> PROMO A </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Example prop </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p>Currently (<b>prior to July 19, 2018</b>), linear attribution would carry forward past the initial conversion and persist into the second conversion </p> 
<ul id="ul_FD09813B59F04FF2A96A70BBE0A8F349"> 
 <li id="li_2EC965DDAE334C1795530F7C6F1674C5">In our first-touch eVar example, the total revenue for each promotion would be calculated using the promos prior to conversion on hit 4 for revenue on hit 4, but all promos for the conversion on hit 7. </li> 
 <li id="li_687C03C4B0A941AA800084F324A95FD6">In our last-touch eVar example, this would be: A = (2/3) * 10 + (2/5) * 5 = $8.66, B = (1/3) * 10 + (2/5) * 5 = $5.33, C = (1/5) * 5 = $1.00. In our FT eVar example: A = (3/3) * 10 + (5/5) * 5 = $15.00, and for the prop: A = (1/2) * 10 + (1/3) * 5 = $6.66, B = (1/2) * 10 + (1/3) * 5 = $6.66, and C = (1/3) * 5 = $1.66. </li> 
</ul> 
<p>Resulting in a distribution as follows: </p> 
<table id="table_6A066E602BF641B0BD4B175EE9753C6E"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> Current Last Touch eVar </th> 
    <th colname="col3" class="entry"> Current First Touch eVar </th> 
    <th colname="col4" class="entry"> Current Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $8.66 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.33 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $1.00 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $1.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p><b>After July 19, 2018</b>, [!DNL Analytics] will treat each sequence of conversions independently, meaning linear attribution will no longer carry forward from one conversion to another. In the previous example, attribution will always be treated the same way (regardless of the eVar allocation settings as stated above) and will be calculated as follows: A = (1/2) * 10 = $5, B = (1/2) * 10 = $5, and C = (1/1) * 5 = $5. To summarize: </p> 
<table id="table_2D39CCD158BF488EA404324DF50B9579"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> New Last Touch eVar </th> 
    <th colname="col3" class="entry"> New First Touch eVar </th> 
    <th colname="col4" class="entry"> New Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

