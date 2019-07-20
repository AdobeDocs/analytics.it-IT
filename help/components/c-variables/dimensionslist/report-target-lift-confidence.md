---
description: Consente di valutare il successo delle campagne in Adobe Analytics come in passato in Target Classic.
seo-description: Consente di valutare il successo delle campagne in Adobe Analytics come in passato in Target Classic.
seo-title: Incremento e confidenza di Target
solution: Analytics
title: Incremento e confidenza di Target
uuid: 00276 cd 2-2 e 0 d -4 a 25-ae 8 a-d 9 f 4 b 30 dd 8 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Incremento e confidenza di Target

Lets you assess the success of campaigns in Adobe Analytics in the same way you have done in [!DNL Target Classic]  in the past.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** &gt; **[!UICONTROL View All Reports]** &gt; **[!UICONTROL Adobe Target]** &gt; **[!UICONTROL Analytics for Target]** &gt; **[!UICONTROL Target Activities]** .

The Adobe Target documentation contains more information on [Lift](https://marketing.adobe.com/resources/help/en_US/target/target/?f=c_estimating_lift_in_revenue) and [Confidence](https://marketing.adobe.com/resources/help/en_US/rec/?f=c_Confidence_Level_and_Confidence_Interval).

Per calcolare Incremento e confidenza:

1. In the **[!UICONTROL Target Activities]** report, click on an activity to bring up its details.
1. Under Report Type, select **[!UICONTROL Lift and Confidence]**.
1. Click **[!UICONTROL Show Metrics]** to add one metric. Non potete aggiungere più metriche per questo tipo di rapporto, in quanto è consigliabile valutare un test in base a una sola metrica. Più metriche aggiungono solo disturbo e riducono il segnale del test.
1. (Optional) Under **[!UICONTROL Normalizing Metric]**, select one of the following: Visitors, Visits, or Impressions. Nella maggior parte dei casi, questo sarà il valore predefinito, Visitatori.

1. Il rapporto aggiungerà queste metriche, compreso il rapporto tra metriche e metriche.

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
   <td colname="col2"> L'attività Target al quale state visualizzando e valutando incremento e confidenza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo di report </td> 
   <td colname="col2"> Qui si seleziona Lift (Incremento) e Confidence (Confidenza), che verranno visualizzati come metriche nei risultati del report di seguito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metriche selezionate </td> 
   <td colname="col2"> Mostra la metrica selezionata (nell'esempio sopra, Revenue (Entrate)), la metrica Normalizzazione (Visitatori univoci), il rapporto tra tali metriche 2 e quindi i calcoli Lift and Confidence (Incremento e Confidenza) in confronto all'Esperienza di controllo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interrotto per </td> 
   <td colname="col2"> Potete suddividere ulteriormente il rapporto in base ad altri rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro dati </td> 
   <td colname="col2"> Consente di applicare filtri specifici a questo rapporto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalizzazione della metrica </td> 
   <td colname="col2"> È possibile normalizzare utilizzando Visite, Visitatori o Impressioni. La metrica normalizzazione diventa il denominatore del calcolo incremento. Inoltre, influenza la modalità di aggregazione dei dati prima dell'applicazione del calcolo di confidenza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Esperienza di controllo </td> 
   <td colname="col2"> L'esperienza Target a cui state confrontando e per il quale state calcolando l'incremento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Confronta con suite di rapporti </td> 
   <td colname="col2"> Consente di scegliere altre suite di rapporti con cui confrontare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Confronta con segmento </td> 
   <td colname="col2"> Consente di scegliere i segmenti con cui confrontare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Percentuale visualizzata come numero/grafico </td> 
   <td colname="col2"> Mostra l'incremento e la percentuale di confidenza come numero o grafico. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Includi dati correnti </td> 
   <td colname="col2"> <p>L'opzione Includi dati correnti in Reporting e analisi consente di visualizzare i dati Analytics più recenti, spesso prima che i dati vengano elaborati e finalizzati completamente. I dati correnti visualizzano la maggior parte delle metriche in minuti, fornendo dati fruibili per una rapida decisione decisionale. </p> </td> 
  </tr> 
 </tbody> 
</table>

