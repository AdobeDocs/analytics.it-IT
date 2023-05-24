---
description: Le metriche calcolate e avanzate calcolate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti.
keywords: Metriche calcolate;Metriche derivate;Metriche calcolate avanzate
title: Metriche calcolate e metriche calcolate avanzate (derivate)
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 602f837689186f232c4c0f8baebbcf911446bc99
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 61%

---

# Metriche calcolate e metriche calcolate avanzate (derivate)

Le metriche calcolate e avanzate calcolate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti.

I nostri strumenti di metriche calcolate offrono un modo altamente flessibile di generare, gestire e curare le metriche. Consentono ad addetti al marketing, product manager e analisti di porre domande sui dati senza dover cambiare l’implementazione [!DNL Analytics]. Le metriche personalizzate disponibili in ogni [!DNL Analytics] pacchetto:

* Adobe [!DNL Analytics] Foundation: calcolato
* [Selezione Adobe Analytics](https://www.adobe.com/it/data-analytics-cloud/analytics/select.html): calcolato + Avanzato calcolato
* [Adobe Analytics Prime](https://www.adobe.com/it/data-analytics-cloud/analytics/prime.html): calcolato + Avanzato calcolato
* [Adobe Analytics Ultimate](https://www.adobe.com/it/data-analytics-cloud/analytics/ultimate.html): calcolato + Avanzato calcolato

Ecco un confronto tra le funzionalità delle metriche calcolate e delle metriche calcolate avanzate:

| Opzioni di generazione | Metriche calcolate | Metriche calcolate avanzate (derivate) |
|---|---|---|
| [Tipi di formato (decimale, ora, percentuale, valuta)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Sì | Sì |
| [Modifiche all’attribuzione (predefinita, lineare, di partecipazione, ecc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sì | Sì |
| [Tipi di metriche (standard, totale)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sì | Sì |
| Operatori di base (aggiungere, sottrarre, moltiplicare, dividere) | Sì | Sì |
| [Applicare i segmenti](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | No | Sì |
| [Funzioni di base (conteggio, valore assoluto, media, ecc.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | No | Sì |
| [Funzioni avanzate (regressione, if/then, t-score, ecc.)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | No | Sì |

## Funzionalità {#section_A0A5C275B68A4D628950BBB0B1EE631F}

È possibile eseguire le seguenti azioni:

* Creare metriche in [!UICONTROL Analysis Workspace], [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection], e [!UICONTROL Contribution Analysis].
* Creare metriche segmentate derivate in fase di esecuzione dei rapporti, senza dover modificare l’implementazione. Questi possono essere visualizzati storicamente perché sono basati su segmenti. Video sulle metriche senza implementazione:

   >[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

* Condividere le metriche tra le suite di rapporti. Ciò significa che tutte le metriche create di recente si applicano a tutte le suite di rapporti nella stessa società di accesso.
* (Solo per metriche calcolate avanzate) Segmento sulle metriche. Ad esempio, puoi creare una metrica per “Nuovi visitatori”, conteggiando le persone per cui questa è la prima sessione. Video sull’argomento:

   >[!VIDEO](https://video.tv.adobe.com/v/25409/?quality=12)

* Incorporare funzioni statistiche per descrivere meglio i dati (solo per metriche calcolate avanzate). Ad esempio, puoi contare il numero di elementi in un rapporto o aggiungere il numero di deviazioni standard per ogni elemento.

## Limitazioni {#section_CB878B02451541D68A68B508D4DBD19A}

Alcuni [!DNL Analytics] Le funzioni di consentono di utilizzare eventi ma non metriche calcolate:

* [!UICONTROL Funnels] in [!UICONTROL Reports & Analytics]
* [!UICONTROL Fallout] in [!UICONTROL Analysis Workspace]
* [!UICONTROL Cohort Analysis] in Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!UICONTROL Real-Time] rapporti
* [!UICONTROL Current Data] rapporti
* [!DNL Analytics] per [!DNL Target]

## Strumenti {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Ecco una breve panoramica della [!UICONTROL Calculated Metrics] strumenti:

<table id="table_520AFE97DB514958ABE23FD3C9CE0ABD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Strumento </th> 
   <th colname="col2" class="entry"> Funzionalità </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md"  > Generatore di metrica calcolata</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E6F02AB9DF204C2F9A0AC92A31594B3E"> 
     <li id="li_A4A6E716374243A190C539A3F4A41C0C">Creare metriche calcolate e calcolate avanzate utilizzando modelli di allocazione avanzati. </li> 
     <li id="li_C8C97BA4E227463E98077ABA5818FFC6">Aggiungere segmenti inline alle formule delle metriche. </li> 
     <li id="li_8503D9E06A3C46569B5CDB4B90F72446">Confrontare segmenti nello stesso rapporto. Ad esempio, confrontare i visitatori locali con quelli internazionali. </li> 
     <li id="li_4B528FDE1F96400DBA0D3276408FF919">Utilizzare le funzioni statistiche. </li> 
     <li id="li_C1162B1EA6784B8189A8A87E2B0DA79A">Fornire descrizioni dettagliate delle metriche (mostrare cosa fanno, dove usarle, dove NON usarle). </li> 
     <li id="li_DEA13F5E8BF94AF1B311C467FE6E2A74">Copiare le definizioni in nuove metriche. </li> 
     <li id="li_8C21F55015D44910904202D2BF74221C">Fornire un’anteprima delle metriche inline. </li> 
     <li id="li_3704F66C321C477F9D4F52E068C231BD">Impostare la polarità della metrica, che indica se è positivo o negativo se un dato evento personalizzato (metrica) aumenta. </li> 
     <li id="li_9D45319FA965476FB1C90DE8AA72BBD7">Applicare tag alle metriche. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md"  > Metriche calcolate Manager</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E4D20D5DD3904CC6A85785B5BD4C1B1E"> 
     <li id="li_E0B216BA1478406EB6212263DF71D85B">Condividere le metriche con altri utenti. </li> 
     <li id="li_96EB16FAF3454211AAEF78EA5B08927F">Approvare e curare le metriche. </li> 
     <li id="li_3ADBD2428EAC4B0AA61222D87C3AF2B7">Organizzare le metriche (assegnare tag) in modo che gli utenti possano trovarle. </li> 
     <li id="li_726F3C3390744E49BA63606FE196880E">Eliminare le metriche. </li> 
     <li id="li_F306BA4FA8AF4A6E987BA62634659A2F">Rinominare le metriche. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Barra del selettore delle metriche </td> 
   <td colname="col2"> <p>Sostituisce il <span class="uicontrol"> Mostra metriche</span> finestra a comparsa in <span class="uicontrol"> Reports &amp; Analytics</span>. </p> <p>Consente di cercare e aggiungere/applicare metriche al rapporto. È inoltre possibile modificare <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-finding.md"  > sort</a> ordine (le opzioni sono: alfabetico, consigliato, usato di frequente, usato di recente). Inoltre, puoi filtrare in base alle suite di rapporti in modo da visualizzare solo le metriche create in una specifica suite di rapporti. </p> <p>Per accedere a questo selettore delle metriche, fai clic sull’icona Metriche <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" width="15px" id="image_2C6F20B4E634486B95BACD4CA47EF991" /> a sinistra di un report. Ecco come appare il selettore delle metriche: </p> <p><img src="assets/metrics_rail.png" width="200px" id="image_379523E9AFEC4CF08D20C42C740AA358" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/README.md"  > API per metriche calcolate</a> </td> 
   <td colname="col2"> <p>Parte del set di API di Adobe Analytics 2.0. </p> </td> 
  </tr> 
 </tbody> 
</table>
