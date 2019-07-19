---
description: nulle
seo-description: nulle
seo-title: Rapporti su Adobe Campaign
title: Rapporti su Adobe Campaign
uuid: 0919 ae 9 f -84 eb -43 a 5-8282-6 cd 6 dec 63 dc 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rapporti su Adobe Campaign

For more information on how to configure this integration, go to the [Adobe Campaign documentation](https://helpx.adobe.com/campaign/standard/integrating/using/about-campaign-analytics-integration.html).

Questa integrazione tra Adobe Analytics e Adobe Campaign

* Consente di condividere i dati KPI (Key Performance Indicator) da Adobe Campaign Standard ad Adobe Analytics.
* Arricchisce le formule di tracciamento con i parametri di Adobe Analytics.
* Adds a new report under  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** &gt; **[!UICONTROL Adobe Campaign.]**
* Aggiunge nuove 5 classificazioni Adobe Campaign.
* Aggiunge altre 10 metriche Adobe Campaign.
* Aggiunge le 6 nuove dimensioni di Adobe Campaign.
* Sincronizza i dati ad Analytics ogni 15 minuti.

## Passaggio 1: Enable Adobe Campaign Reporting {#section_C685EF10505045708A6536BB13F6CD58}

Per visualizzare i dati della campagna in Analytics, devi prima abilitare i rapporti Campagna.

1. Navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL <select report suite>]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Adobe Campaign]** &gt; **[!UICONTROL Adobe Campaign Reporting]** .
1. Fai clic su **[!UICONTROL Enable Campaign Reporting]**.

   ![](assets/enable-campaign.png)

## Passaggio 2: View Adobe Campaign Reports {#section_9C18A29F3CC54BD4AC5EA96417F17B33}

The integration between Adobe Campaign Standard and Adobe Analytics adds the following report under  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**

<table id="table_3627F40DC90646A7B5E217A88B6FD630"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Report </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID consegna eseguito Adobe Campaign </p> </td> 
   <td colname="col2"> <p>Mostra i dati importati da Adobe Campaign sulle e-mail inviate da Adobe Campaign. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Passaggio 3: Use Adobe Campaign Classifications {#section_74A28AF3F4CA4091943789DE4D8B2B63}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL <select report suite>]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Adobe Campaign]** &gt; **[!UICONTROL Adobe Campaign Classifications]**

Una volta abilitata la suite di rapporti per Adobe Campaign, sono disponibili le seguenti classificazioni:

* ID consegna (nome consegna interna visualizzato in Campaign)
* Etichetta consegna ((Consegna in Campaign - Consegna singola/Consegna periodica/Consegna transazione)
* ID campagna (Nome campagna interno visualizzato in Campaign)
* Etichetta campagna (Campagna in Adobe Campaign)
* Etichetta consegna eseguito (elenco di singole consegne eseguite)

## Adobe Campaign Dimensions and Metrics available in Adobe Analytics {#section_F33385C9660644AF84172EC39601469B}

The following **metrics** are available from Campaign in Adobe Analytics report suites:

* Adobe Campaign Sent
* Adobe Campaign aperta
* Adobe Campaign fa clic su
* Adobe Campaign elaborata
* Adobe Campaign Delivered
* Adobe Campaign Unique Open
* Clic univoco su Adobe Campaign
* Adobe Campaign Unsubscri
* Adobe Campaign Total Bounses
* Istanze ID consegna esecuzione Adobe Campaign

The following **dimensions** are available from Campaign in Adobe Analytics report suites:

| Nome dimensione | Definizione |
|--- |--- |
| ID campagna | ID di tutte le campagne per le quali è stato inviato KPI durante la durata |
| Etichetta campagna | Etichette degli ID campagna |
| ID consegna | ID di tutte le consegne per le quali è stato inviato KPI durante la durata. Include anche ID di consegne principali di consegna periodica e consegna transazione. Esempio: Una consegna ricorrente DM 1 è stata pianificata e DM 2, DM 3, DM 4 e DM 5 sono consegne secondarie di consegna ricorrente. L'ID consegna visualizza i risultati per tutte le consegne, da DM 1 a DM 5. |
| Etichetta consegna | Etichette di ID consegna |
| ID consegna eseguito | ID di sole consegne eseguite. Nessun ID della consegna principale ricorrente/transazionale. Esempio: Una consegna ricorrente DM 1 è stata pianificata e DM 2, DM 3, DM 4 e DM 5 sono consegne secondarie di consegna ricorrente. L'ID consegna eseguito visualizza i risultati per tutte le consegne a partire da DM 2 a DM 5, le consegne che sono state eseguite. |
| Etichetta consegna eseguita | Etichette degli ID di consegna eseguiti |
