---
description: Consente di valutare il successo delle campagne in Adobe Analytics nello stesso modo in cui lo facevate in Target Classic in passato.
seo-description: Consente di valutare il successo delle campagne in Adobe Analytics nello stesso modo in cui lo facevate in Target Classic in passato.
seo-title: Incremento e confidenza Target
solution: Analytics
title: Incremento e confidenza Target
uuid: 00276cd2-2e0d-4a25-ae8a-d9f4b30dd8ba
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Incremento e confidenza Target

Lets you assess the success of campaigns in Adobe Analytics in the same way you have done in [!DNL Target Classic]  in the past.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** &gt; **[!UICONTROL View All Reports]** &gt; **[!UICONTROL Adobe Target]** &gt; **[!UICONTROL Analytics for Target]** &gt; **[!UICONTROL Target Activities]** .

La documentazione di Adobe Target contiene ulteriori informazioni su [Lift](https://marketing.adobe.com/resources/help/en_US/target/target/c_estimating_lift_in_revenue.html) e [Confidence](https://marketing.adobe.com/resources/help/en_US/rec/c_Confidence_Level_and_Confidence_Interval.html).

Per calcolare l'incremento e la confidenza:

1. Nel **[!UICONTROL Target Activities]** rapporto, fate clic su un'attività per visualizzarne i dettagli.
1. In Tipo rapporto, selezionare **[!UICONTROL Lift and Confidence]**.
1. Fate clic **[!UICONTROL Show Metrics]** per aggiungere una metrica. Non è possibile aggiungere più di una metrica per questo tipo di rapporto, poiché è consigliabile valutare un test in base a una sola metrica. Più metriche aggiungerebbero solo rumore e ridurrebbero il segnale del test.
1. (Facoltativo) In **[!UICONTROL Normalizing Metric]**, selezionare una delle opzioni seguenti: Visitatori, Visite o Impressioni. Nella maggior parte dei casi, questo sarà il valore predefinito, Visitatori.

1. Il report aggiungerà queste metriche, incluso il rapporto tra le metriche e la metrica di normalizzazione.

## Impostazioni dei rapporti {#section_3508439E09CA4E38B2EA309BA477C01D}

![](assets/lift_confidence_ui.png)

<table id="table_0FBB257C96454CDA82D487DC68459C13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Attività selezionata </td> 
   <td colname="col2"> L'attività Target per la quale state visualizzando e calcolando l'incremento e la confidenza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo di report </td> 
   <td colname="col2"> Qui si seleziona Solleva e Confidenza, che verranno visualizzate come metriche nei risultati del rapporto riportati di seguito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metriche selezionate </td> 
   <td colname="col2"> Mostra la metrica selezionata (nell'esempio sopra, Revenue), la metrica di normalizzazione (Visitatori unici), il rapporto tra queste 2 metriche, quindi i calcoli Lift and Confidence rispetto all'Esperienza di controllo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suddiviso per </td> 
   <td colname="col2"> Potete inoltre suddividere il rapporto con altri rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro dati </td> 
   <td colname="col2"> Consente di applicare filtri specifici a questo rapporto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalizzazione della metrica </td> 
   <td colname="col2"> Puoi normalizzare tramite Visite, Visitatori o Impressioni. La metrica di normalizzazione diventa il denominatore del calcolo dell'incremento. Inoltre, influisce sul modo in cui i dati vengono aggregati prima dell'applicazione del calcolo del valore di confidenza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Esperienza di controllo </td> 
   <td colname="col2"> Esperienza Target a cui si sta confrontando e per la quale si sta calcolando l'incremento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Confronta con suite di rapporti </td> 
   <td colname="col2"> Consente di scegliere altre suite di rapporti da confrontare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Confronta con segmento </td> 
   <td colname="col2"> Consente di scegliere i segmenti a cui confrontare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Percentuale visualizzata come numero/grafico </td> 
   <td colname="col2"> Mostra la percentuale di incremento e confidenza come numero o grafico. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Includi dati correnti </td> 
   <td colname="col2"> <p>L'opzione Includi dati correnti in Reporting e analisi consente di visualizzare gli ultimi dati di Analytics, spesso prima che i dati vengano elaborati e finalizzati completamente. I dati correnti mostrano la maggior parte delle metriche in pochi minuti, fornendo dati fruibili per il processo decisionale rapido. </p> </td> 
  </tr> 
 </tbody> 
</table>

