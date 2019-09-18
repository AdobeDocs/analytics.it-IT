---
description: Mostra il numero di visitatori univoci che hanno effettuato l’accesso al sito. Ogni visitatore viene conteggiato una volta, indipendentemente dal numero di visite effettuate dal visitatore del sito Web.
seo-description: Mostra il numero di visitatori univoci che hanno effettuato l’accesso al sito. Ogni visitatore viene conteggiato una volta, indipendentemente dal numero di visite effettuate dal visitatore del sito Web.
seo-title: Visitatori unici
solution: Analytics
title: Visitatori unici
topic: Rapporti
uuid: e70e1a14-b3b9-4d1a-a8a5-a247a443c752
translation-type: tm+mt
source-git-commit: 646d6e01d0f0201c78117ee9bf9ff64fda9a026a

---


# Visitatori unici

Mostra il numero di visitatori univoci che hanno effettuato l’accesso al sito. Ogni visitatore viene conteggiato una volta, indipendentemente dal numero di visite effettuate dal visitatore del sito Web.

**Dati di esempio**

Fare riferimento alla tabella seguente per gli esempi in questa pagina. Lo stesso visitatore è rappresentato qui:

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

## Rapporto Visitatori unici - Metrica con tendenze {#section_372C08A881D34BBF811C1DE0A1460617}

[!UICONTROL Unique Visitors] i rapporti si comportano in modo simile in Analisi ad hoc. Per ogni hit in cui si verifica la visita, il visitatore viene conteggiato sull’hit. Ogni pagina riceve credito avendo il visitatore su quella pagina.

<table id="table_7D9119045E8243698B6BB2E8C93F6B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col2" class="entry"> Visitatori unici </th> 
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

Inoltre, ogni data riceve credito per aver avuto quel visitatore in quella data.

<table id="table_E0D06D9434444947BDA818F61A580B65"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitatori unici </th> 
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

**[!UICONTROL Unique Visitors Report]Broken Down by *`Page`*.**

È possibile selezionare una pagina per [!UICONTROL Unique Visitors Report]. Nel seguente rapporto, il visitatore visita la pagina A nelle seguenti date:

<table id="table_2ABA17B19E0D4F92AAB003BE784DA9E0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitatori unici </th> 
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

## Visitatori univoci basati su periodi (con tendenze) {#section_B3502EBF1ACB487AA8E0EFBA9A0561FD}

Potete eseguire ogni ora, giorno, settimana, mese, trimestrale e annuale [!UICONTROL Unique Visitors Reports] (con tendenze).

I visitatori univoci basati sul periodo vengono conteggiati solo per la prima visita nel periodo specificato. Ad esempio, i visitatori unici orari vengono conteggiati per la prima visita durante l’ora specificata. I Visitatori univoci giornalieri vengono conteggiati per la prima visita nel giorno specificato.

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

Il rapporto seguente verrà visualizzato per Visitatori giornalieri univoci.

<table id="table_4E44BC4722064501A5B648BE80ED8E60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitatori giornalieri unici </th> 
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

I totali delle metriche possono variare in base all'intervallo di date del rapporto. I rapporti di marketing iniziano a contare i visitatori unici basati sul tempo dall'inizio dell'intervallo di date. Ad esempio, se l’intervallo di date è compreso tra il 2 e il 3 gennaio, per i visitatori unici settimanali verranno mostrati i seguenti risultati:

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

Puoi utilizzare la segmentazione per modificare l’intervallo di date in modo da includere date successive anziché date precedenti. Ad esempio, si supponga che l'intervallo di date sia ancora compreso tra il 2 e il 3 gennaio (come illustrato nella tabella precedente). Se applicate un segmento in cui Pagina = C, il 2 gennaio non supererà il segmento e il primo hit del visitatore univoco settimanale sarà il 3 gennaio. Se invece avete applicato un segmento in cui Pagina = D, entrambi i segmenti saranno esclusi il 2 gennaio e il 3 gennaio. Nessun risultato verrà visualizzato per il visitatore univoco settimanale e verrà escluso dal totale.

**Report Visitatori univoci basati su periodi **

Questi rapporti utilizzano una pagina, un prop e un attributo particolari (ad esempio: dove Page = A).

Supponiamo che tu abbia come tendenza [!UICONTROL Pages Report] una metrica Visitatore unico basata su un periodo. Se è selezionata una suddivisione o una variabile per i rapporti Visitatori unici basati sul periodo, i rapporti di marketing contano tutte le istanze univoche della coppia visitatore/attributo. Per il primo hit del visitatore, questa elaborazione non è diversa dagli esempi precedenti. Per gli hit successivi, questi rapporti includono hit che i rapporti sopra indicati non riportano, se la pagina è diversa.

Per i visitatori unici settimanali in cui Pagina = A, i rapporti di marketing escludono il 2 gennaio dai totali. Questa esclusione si verifica perché i rapporti di marketing contavano già il Visitatore univoco settimanale il 1 gennaio. Di seguito è riportato un rapporto settimanale dei visitatori univoci in cui Pagina = A:

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

Per i visitatori unici settimanali in cui Page = B, l'unica data in cui si verifica è il 2 gennaio, come illustrato di seguito:

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

## Metriche del visitatore univoche basate su periodi sui report non con tendenze {#section_90B784F4E49F4930B3F0923B95958BA2}

Puoi aggiungere metriche Visitatore univoco basate su un periodo ai report non con tendenze, ad esempio una metrica Visitatori unici settimanali su un [!UICONTROL Pages Report].

<table id="table_8651A42696B0404CAEAE0FC5522CC1C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col02" class="entry"> Data della visita </th> 
   <th colname="col2" class="entry"> Visite - Visitatore unico settimanale </th> 
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

Una metrica Visitatori univoci giornalieri su un [!UICONTROL Pages Report] elemento mostra:

<table id="table_04C7C305C2B945D6A79A6B80F48A4BF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col02" class="entry"> Data della visita </th> 
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
   <td colname="col2"> <p>4 Visitatori unici giornalieri </p> </td> 
  </tr> 
 </tbody> 
</table>

Per suddividere un attributo per un altro (ad esempio *`page`* per *`eVar`*), Analytics assegna un visitatore univoco basato sul periodo per ogni istanza univoca del periodo e della pagina (o l'attributo associato).

Se si suddivide la pagina A per eVar T, U, gennaio 2 è esclusa perché la pagina A è stata visualizzata il 1 gennaio. I risultati seguenti verranno visualizzati per Visitatori unici settimanali:

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

## Cookie persistenti {#section_81E139F08AEB4E30A06472856975EA1E}

I cookie persistenti si trovano sul computer di un visitatore tra una visita e l'altra, in modo che Adobe possa identificare i visitatori nelle visite successive. Per visualizzare la percentuale di utenti che accettano o meno i cookie persistenti, selezionare **[!UICONTROL Filter]** &gt; **[!UICONTROL Persistent Cookies]**.

Il grafico e la visualizzazione dei dettagli riportati di seguito mostrano sia i visitatori con cookie persistenti che quelli con cookie non persistenti. Nella maggior parte dei casi, il numero di visitatori con cookie non persistenti è trascurabile.
