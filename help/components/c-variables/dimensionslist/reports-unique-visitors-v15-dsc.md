---
description: Mostra il numero di visitatori unici che hanno effettuato l'accesso al sito. Ogni visitatore viene conteggiato una volta, a prescindere dal numero di visite visitate dal sito Web.
seo-description: Mostra il numero di visitatori unici che hanno effettuato l'accesso al sito. Ogni visitatore viene conteggiato una volta, a prescindere dal numero di visite visitate dal sito Web.
seo-title: Visitatori univoci
solution: Analytics
title: Visitatori univoci
topic: Rapporti
uuid: e 70 e 1 a 14-b 3 b 9-4 d 1 a-a 8 a 5-a 247 a 443 c 752
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visitatori univoci

Mostra il numero di visitatori unici che hanno effettuato l'accesso al sito. Ogni visitatore viene conteggiato una volta, a prescindere dal numero di visite visitate dal sito Web.

**Dati di esempio**

Per esempi su questa pagina, fare riferimento alla tabella seguente. Lo stesso visitatore è rappresentato qui:

<table id="table_4F54873A4ED8451494E466C2BDB15B00"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> 1/1/2017 </th> 
   <th colname="col3" class="entry"> 1/1/2017 </th> 
   <th colname="col4" class="entry"> 1/2/2017 </th> 
   <th colname="col5" class="entry"> 1/2/2017 </th> 
   <th colname="col6" class="entry"> 1/2/2017 </th> 
   <th colname="col7" class="entry"> 1/3/2017 </th> 
   <th colname="col8" class="entry"> 1/4/2017 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pagina </p> </td> 
   <td colname="col2"> <p>Una  </p> </td> 
   <td colname="col3"> <p>C </p> </td> 
   <td colname="col4"> <p>Una  </p> </td> 
   <td colname="col5"> <p>B </p> </td> 
   <td colname="col6"> <p>C </p> </td> 
   <td colname="col7"> <p>D </p> </td> 
   <td colname="col8"> <p>E </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar </p> </td> 
   <td colname="col2"> <p>T, U </p> </td> 
   <td colname="col3"> <p>V </p> </td> 
   <td colname="col4"> <p>W </p> </td> 
   <td colname="col5"> <p> </p> </td> 
   <td colname="col6"> <p>X, Y </p> </td> 
   <td colname="col7"> <p>Z </p> </td> 
   <td colname="col8"> <p>Z </p> </td> 
  </tr> 
 </tbody> 
</table>

## Unique Visitors Report - Trended Metric {#section_372C08A881D34BBF811C1DE0A1460617}

[!UICONTROL Unique Visitors] I rapporti si comportano in modo simile in Analisi ad hoc. Per ogni hit in cui si verifica la visita, il visitatore viene conteggiato su quell'hit. Ogni pagina riceve credito con il visitatore sulla pagina.

<table id="table_7D9119045E8243698B6BB2E8C93F6B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col2" class="entry"> Visitatori univoci </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Una  </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

Inoltre, ogni data riceve credito per il visitatore entro tale data.

<table id="table_E0D06D9434444947BDA818F61A580B65"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitatori univoci </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 gennaio </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 3 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 4 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

** [!UICONTROL Unique Visitors Report] Broken Down by *`Page`*.**

You can select a page for [!UICONTROL Unique Visitors Report]. Nel report seguente, il visitatore visita la pagina A nelle date seguenti:

<table id="table_2ABA17B19E0D4F92AAB003BE784DA9E0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitatori univoci </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 gennaio </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 4 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Period-Based Unique Visitors (Trended) {#section_B3502EBF1ACB487AA8E0EFBA9A0561FD}

You can run Hourly, Daily, Weekly, Monthly, Quarterly, and Yearly [!UICONTROL Unique Visitors Reports] (trended).

I visitatori univoci basati su periodo vengono conteggiati solo alla prima visita nel periodo specificato. Ad esempio, i visitatori unici orari vengono conteggiati per la prima visita nell'ora specificata. Visitatori giornalieri unici vengono conteggiati per la prima visita nel giorno specificato.

<table id="table_FF14F05CDFDA4F2E92A62D9D751A1CAA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitatori unici settimanali </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 gennaio </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 2 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 4 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

Il report seguente viene visualizzato per Visitatori giornalieri univoci.

<table id="table_4E44BC4722064501A5B648BE80ED8E60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitatori giornalieri univoci </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 gennaio </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 3 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 4 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col2"> <p>4 </p> </td> 
  </tr> 
 </tbody> 
</table>

I totali delle metriche possono variare in base all'intervallo di date del report. I rapporti di marketing iniziano a conteggiare Visitatori unici basati sul tempo dall'inizio dell'intervallo di date. Ad esempio, se l'intervallo di date è compreso tra il 2 gennaio e il 3 gennaio, i risultati indicati di seguito vengono mostrati per Visitatori unici settimanali:

<table id="table_B695708BB22949E7BA293FE492D2EEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitatori unici settimanali </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gennaio 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

**Segmentazione**

Puoi utilizzare la segmentazione per cambiare l'intervallo di date in modo da includere date successive invece delle date precedenti. Ad esempio, si supponga che l'intervallo di date sia ancora compreso tra il 2 gennaio e il 3 gennaio (come mostrato nella tabella precedente). Se applichi un segmento in cui Page = C, January 2 non passa il segmento, il primo hit del visitatore Unique Unique sarà il 3 gennaio. Se invece avete applicato un segmento in cui Page = D, sia il 2 gennaio che il 3 gennaio verrebbero esclusi. Per il visitatore Unique unitor non vengono visualizzati risultati che verrebbero esclusi dal totale.

** Rapporti visitatori univoci basati su punti**

Tali rapporti utilizzano una pagina, un prop e un attributo particolari (ad esempio: dove Page = A).

Suppose that you trend a [!UICONTROL Pages Report] with a period-based Unique Visitor metric. Se per i rapporti Visitatori unici basati su punti è selezionata una suddivisione o una variabile, i rapporti di marketing contano tutte le istanze univoche della coppia di visitatore e attributo. Per il primo hit del visitatore, l'elaborazione non è diversa dagli esempi precedenti. Per gli hit successivi, questi rapporti includono hit che i rapporti indicati non sono in grado di supportare, se la pagina è diversa.

Per Visitatori unici settimanali in cui Page = A, i rapporti di marketing escludono il 2 gennaio dai totali. Questa esclusione si verifica perché i rapporti di marketing hanno già conteggiato il visitatore Unique Unique il 1 gennaio. Ecco un rapporto settimanale su visitatori univoci dove Page = A:

<table id="table_9C5E00029C7340B28D76696E84F66511"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitatori unici settimanali </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 gennaio </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 2 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 4 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

Per visitatori unici settimanali in cui Pagina = B, l'unica data in cui si verifica è gennaio 2, come illustrato:

<table id="table_262150BECCB74120B58F506F4BC6F629"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visite - Visitatori unici settimanali </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 gennaio </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gennaio 4 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Period-Based Unique Visitor Metrics on Non-Trended Reports {#section_90B784F4E49F4930B3F0923B95958BA2}

You can add period-based Unique Visitor metrics to non-trended reports, such as a Weekly Unique Visitors metric on a [!UICONTROL Pages Report].

<table id="table_8651A42696B0404CAEAE0FC5522CC1C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col02" class="entry"> Data di visita </th> 
   <th colname="col2" class="entry"> Visite - Visitatore univoco settimanale </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Una  </p> </td> 
   <td colname="col02"> <p>1 gennaio </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col02"> <p>Gennaio 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col02"> <p>Gennaio 3 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col02"> <p>Gennaio 4 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E </p> </td> 
   <td colname="col02"> <p>Gennaio 5 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col02"> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

A Daily Unique Visitors metric on a [!UICONTROL Pages Report] would show:

<table id="table_04C7C305C2B945D6A79A6B80F48A4BF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col02" class="entry"> Data di visita </th> 
   <th colname="col2" class="entry"> Visite </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Una  </p> </td> 
   <td colname="col02"> <p>1 gennaio </p> </td> 
   <td colname="col2"> <p>2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col02"> <p>Gennaio 2 </p> </td> 
   <td colname="col2"> <p>2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col02"> <p>Gennaio 3 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col02"> <p>Gennaio 4 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col02"> <p> </p> </td> 
   <td colname="col2"> <p>4 Visitatori giornalieri univoci </p> </td> 
  </tr> 
 </tbody> 
</table>

To break down one attribute by another (such as *`page`* by *`eVar`*), Analytics allocates a period-based Unique Visitor for each unique instance of the period and page (or the attribute being correlated).

Se hai interrotto la Pagina A per evar T, U, January 2 viene esclusa perché la Pagina A è stata visualizzata il 1 gennaio. I risultati seguenti vengono visualizzati per Visitatori unici settimanali:

<table id="table_328A6F2E920A44B3B55A6E6A630F6DBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar </th> 
   <th colname="col2" class="entry"> Visitatori unici settimanali </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>T </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>U </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Persistent Cookies {#section_81E139F08AEB4E30A06472856975EA1E}

I cookie persistenti rimangono sul computer di un visitatore tra visite, in modo che Adobe possa identificare i visitatori nelle visite successive. To see the percentage of users who do and do not accept persistent cookies, select **[!UICONTROL Filter]** &gt; **[!UICONTROL Persistent Cookies]**.

Il grafico e la visualizzazione dei dettagli di seguito mostrano sia i visitatori persistenti che i visitatori non persistenti. Nella maggior parte dei casi, il numero di visitatori non persistenti è trascurabile.
