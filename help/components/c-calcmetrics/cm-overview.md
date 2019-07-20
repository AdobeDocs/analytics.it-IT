---
description: Le metriche calcolate e calcolate calcolate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti.
keywords: Metriche calcolate; Metriche derivate; Metriche calcolate avanzate
seo-description: Le metriche calcolate e calcolate calcolate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti.
seo-title: Metriche calcolate e calcolate calcolate (derivate)
title: Metriche calcolate e calcolate calcolate (derivate)
uuid: 2553 c 115-b 15 a -4109-8 de 2-733 dbc 1 eeb 9 e
translation-type: tm+mt
source-git-commit: fb27d500a725a540e632952295aa2ea3a3a21fb6

---


# Metriche calcolate e calcolate calcolate (derivate)

Le metriche calcolate e calcolate calcolate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti.

>[!IMPORTANT]
>
>In July 2018, Adobe introduced [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), which revised the way allocation models in calculated metrics are evaluated. Come parte di questa modifica, le metriche calcolate che utilizzano un modello di assegnazione non predefinito sono state trasferite a nuovi modelli di attribuzione migliorati:
>
>* I modelli di allocazione «Last Channel Last Touch» (Ultimo contatto) e «Marketing Channel First Touch» (Primo contatto canale di marketing) sono stati migrati rispettivamente ai nuovi modelli di attribuzione «Last Touch» e «First Touch» (Nota: «Marketing Channels» non è obsoleto - sono stati registrati solo i due modelli di allocazione che compaiono nelle metriche calcolate.
>* Inoltre, è stato corretto il modo in cui viene calcolato l'allocazione lineare. Per i clienti che usano metriche calcolate con modelli di allocazione "Linear", i report possono variare leggermente per riflettere il nuovo modello di attribuzione corretto. This change to calculated metrics is reflected in [!UICONTROL Analysis Workspace], [!UICONTROL Reports & Analytics], the Reporting API, Report Builder, and Ad Hoc Analysis. For more information, see [How Linear Allocation will work as of July 19, 2018](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1).


Gli strumenti Metriche calcolate offrono un modo altamente flessibile di creare, gestire e curare le metriche. They allow you as marketers, product managers and analysts to ask questions of the data without having to change your [!DNL Analytics] implementation. The custom metrics available in each [!DNL Analytics] package are:

* Adobe [!DNL Analytics] Foundation: Calculated
* [Adobe Analytics seleziona](https://www.adobe.com/data-analytics-cloud/analytics/select.html): Calcolato + Advanced Calcolato
* [Adobe Analytics Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html): Calcolato + Advanced Calcolato
* [Adobe Analytics Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html): Calcolato + Advanced Calcolato

Ecco un confronto tra le funzionalità Metriche calcolate e Metriche calcolate avanzate:

| Opzioni del generatore | Metriche calcolate | Metriche calcolate (derivate) avanzate |
|---|---|---|
| [Tipi di formato (decimale, ora, percentuale, valuta)](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#concept_5EC82A91EB9C44FC870326C85F9D0B18) | Sì | Sì |
| [Modifiche di attribuzione (impostazione predefinita, lineare, partecipazione, ecc.)](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) | Sì | Sì |
| [Tipi di metrica (standard, totale)](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) | Sì | Sì |
| Operatori di base (Aggiungi, sottrae, moltiplica, dividi) | Sì | Sì |
| [Applicare i segmenti](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md#concept_21C77BD86E7E45E79AF030D8ED54DB3E) | No | Sì |
| [Funzioni di base (count, abs value, mean, etc)](../../components/c-calcmetrics/cm-reference/cm-functions.md#concept_E3022D5EEEE145B69A23438BAF7016B2) | No | Sì |
| [Funzioni avanzate (regressione, se/then, t-score, ecc.)](../../components/c-calcmetrics/cm-reference/cm-adv-functions.md#concept_A5FB9127D70F4E1AA02D1ACBF4F54174) | No | Sì |

## Funzionalità {#section_A0A5C275B68A4D628950BBB0B1EE631F}

È possibile

* Create metrics across [!UICONTROL Analysis Workspace], [!UICONTROL Reports & Analytics], [!UICONTROL Ad Hoc Analysis], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis].
* Create segmented metrics that are derived at report run time, [without having to change the implementation](https://youtu.be/CuQTm9RaUpY). Questi possono essere visualizzati in modo cronologico perché sono basati sui segmenti.
* Condividi metriche nelle suite di rapporti. Ciò significa che tutte le metriche appena create si applicano a tutte le suite di rapporti nella stessa società di accesso.
* (Solo Metriche calcolate avanzate) Segmento sulle metriche. Ad esempio, potete creare una metrica per «New visitors» (Nuovi visitatori), con un numero di persone per le quali si tratta della prima sessione.
* (Solo Metriche calcolate avanzate) Incorporate funzioni statistiche per descrivere meglio i dati. Ad esempio, è possibile calcolare il numero di elementi in un rapporto o aggiungere al numero di deviazioni standard per ogni elemento.
* Utilize metrics created in [!UICONTROL Ad Hoc Analysis] in the other [!DNL Analytics] tools and vice versa.

   >[!NOTE]
   >
   >Puoi continuare a creare metriche in Analisi ad hoc. L'interfaccia utente del generatore di metriche calcolate è simile al nuovo generatore di metriche.

## Limitazioni {#section_CB878B02451541D68A68B508D4DBD19A}

Some [!DNL Analytics] features let you use events but not calculated metrics:

* [!UICONTROL Funnels] in [!UICONTROL Reports & Analytics]
* [!UICONTROL Fallout] in [!UICONTROL Analysis Workspace]
* [!UICONTROL Cohort Analysis] in Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!UICONTROL Real-Time] rapporti
* [!UICONTROL Current Data] rapporti
* [!DNL Analytics] per [!DNL Target]

## Strumenti {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Here is a short overview of the [!UICONTROL Calculated Metrics] tools:

<table id="table_520AFE97DB514958ABE23FD3C9CE0ABD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Strumento </th> 
   <th colname="col2" class="entry"> Funzionalità </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#concept_5EC82A91EB9C44FC870326C85F9D0B18" format="dita" scope="local"> Generatore di metrica calcolata</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E6F02AB9DF204C2F9A0AC92A31594B3E"> 
     <li id="li_A4A6E716374243A190C539A3F4A41C0C">Crea metriche calcolate e avanzate calcolate utilizzando modelli di assegnazione avanzati. </li> 
     <li id="li_C8C97BA4E227463E98077ABA5818FFC6">Aggiungi segmenti in linea alle formule delle metriche. </li> 
     <li id="li_8503D9E06A3C46569B5CDB4B90F72446">Confronta i segmenti nello stesso rapporto. Ad esempio, confronta i visitatori locali con i visitatori internazionali. </li> 
     <li id="li_4B528FDE1F96400DBA0D3276408FF919">Utilizzare le funzioni statistiche. </li> 
     <li id="li_C1162B1EA6784B8189A8A87E2B0DA79A">Fornite descrizioni metriche dettagliate (mostra cosa accade, dove utilizzarlo, dove NON per utilizzarlo). </li> 
     <li id="li_DEA13F5E8BF94AF1B311C467FE6E2A74">Copia definizioni in nuove metriche. </li> 
     <li id="li_8C21F55015D44910904202D2BF74221C">Fornisce un'anteprima della metrica in linea. </li> 
     <li id="li_3704F66C321C477F9D4F52E068C231BD">Imposta la polarità delle metriche, che indica se è buona o insoddisfacente se un determinato evento personalizzato viene rilasciato. </li> 
     <li id="li_9D45319FA965476FB1C90DE8AA72BBD7">Metriche tag. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md#concept_BA6815CB06D842D5825766396B691653" format="dita" scope="local"> Gestore metriche calcolate</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E4D20D5DD3904CC6A85785B5BD4C1B1E"> 
     <li id="li_E0B216BA1478406EB6212263DF71D85B">Condividi metriche con altri. </li> 
     <li id="li_96EB16FAF3454211AAEF78EA5B08927F">Approvare e curare le metriche. </li> 
     <li id="li_3ADBD2428EAC4B0AA61222D87C3AF2B7">Organizza (tag) le tue metriche in modo che le persone possano trovarle. </li> 
     <li id="li_726F3C3390744E49BA63606FE196880E">Eliminare le metriche. </li> 
     <li id="li_F306BA4FA8AF4A6E987BA62634659A2F">Rinominare le metriche. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Barra di selezione metrica </td> 
   <td colname="col2"> <p>Replaces the <span class="uicontrol"> Show Metrics</span> popup in [!UICONTROL Reports &amp; Analytics]. </p> <p>Consente di cercare e aggiungere/applicare metriche al rapporto. You can also change the <a href="../../components/c-calcmetrics/c-workflow/cm-workflow/cm-finding.md#concept_A09845053A934CB7B755391D76E76C08" format="dita" scope="local"> sort</a> order (options are: alphabetical, recommended, frequently used, recently used.) Inoltre, puoi filtrare sulle suite di rapporti per mostrare solo le metriche create in una suite di rapporti specifica. </p> <p>To access this Metric Selector, click the Metrics icon <img placement="inline"  src="assets/metrics_icon.png" width="30px" id="image_2C6F20B4E634486B95BACD4CA47EF991" /> to the left of a report. Questo è l'aspetto del Selettore metrica: </p> <p><img placement="break" align="center"  src="assets/metrics_rail.png" width="200px" id="image_379523E9AFEC4CF08D20C42C740AA358" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/README.md" format="https" scope="external"> API per metriche calcolate</a> </td> 
   <td colname="col2"> <p>Parte della serie API di Adobe Analytics 2.0. </p> </td> 
  </tr> 
 </tbody> 
</table>

