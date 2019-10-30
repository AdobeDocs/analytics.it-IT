---
description: nulle
seo-description: nulle
seo-title: Reportistica di Adobe Campaign
title: Reportistica di Adobe Campaign
uuid: 0919ae9f-84eb-43a5-8282-6cd6dec63dc1
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Reportistica di Adobe Campaign

Per ulteriori informazioni su come configurare questa integrazione, consulta la documentazione [di](https://helpx.adobe.com/campaign/standard/integrating/using/about-campaign-analytics-integration.html)Adobe Campaign.

Questa integrazione tra Adobe Analytics e Adobe Campaign

* Consente di condividere i dati KPI (Key Performance Indicator) da Adobe Campaign Standard ad Adobe Analytics.
* Arricchisce le formule di tracciamento con i parametri di Adobe Analytics.
* Aggiunge un nuovo rapporto in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** &gt; **[!UICONTROL Adobe Campaign.]**
* Aggiunge 5 nuove classificazioni di Adobe Campaign.
* Aggiunge 10 nuove metriche di Adobe Campaign.
* Aggiunge 6 nuove dimensioni di Adobe Campaign.
* Sincronizza i dati con Analytics ogni 15 minuti.

## Passaggio 1: Abilita rapporti Adobe Campaign {#section_C685EF10505045708A6536BB13F6CD58}

Per visualizzare i dati delle campagne in Analytics, devi prima abilitare il reporting delle campagne.

1. Navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL <select report suite>]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Adobe Campaign]** &gt; **[!UICONTROL Adobe Campaign Reporting]** .
1. Fai clic su **[!UICONTROL Enable Campaign Reporting]**.

   ![](assets/enable-campaign.png)

## Passaggio 2: Visualizzare i rapporti di Adobe Campaign {#section_9C18A29F3CC54BD4AC5EA96417F17B33}

L'integrazione tra Adobe Campaign Standard e Adobe Analytics aggiunge il seguente rapporto in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**

<table id="table_3627F40DC90646A7B5E217A88B6FD630"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Report </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID consegna eseguita da Adobe Campaign </p> </td> 
   <td colname="col2"> <p>Mostra i dati importati da Adobe Campaign sulle e-mail inviate da Adobe Campaign. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Passaggio 3: Usa classificazioni Adobe Campaign {#section_74A28AF3F4CA4091943789DE4D8B2B63}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL <select report suite>]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Adobe Campaign]** &gt; **[!UICONTROL Adobe Campaign Classifications]**

Quando la suite di rapporti è abilitata per Adobe Campaign, sono disponibili le seguenti classificazioni:

* ID consegna (nome di consegna interno visualizzato in Campaign)
* Etichetta di consegna (consegna nella campagna - Consegna individuale/Consegna ricorrente/Consegna transazione)
* ID campagna (nome campagna interna visibile in Campaign)
* Etichetta campagna (Campaign in Adobe Campaign)
* Etichetta consegna eseguita (elenco di singole consegne eseguite)

## Dimensioni e metriche di Adobe Campaign disponibili in Adobe Analytics {#section_F33385C9660644AF84172EC39601469B}

Le seguenti **metriche** sono disponibili da Campaign nelle suite di rapporti di Adobe Analytics:

* Adobe Campaign Inviato
* Adobe Campaign Opened
* Adobe Campaign Click
* Adobe Campaign Elaborato
* Adobe Campaign
* Adobe Campaign Unique Open
* Adobe Campaign Unique Click
* Adobe Campaign Unsubscription
* Totale bacheche di Adobe Campaign
* Istanze ID consegna eseguito da Adobe Campaign

Le seguenti **dimensioni** sono disponibili da Campaign nelle suite di rapporti di Adobe Analytics:

| Nome dimensione | Definizione |
|--- |--- |
| ID campagna | ID di tutte le campagne per le quali sono stati inviati KPI durante la durata |
| Etichetta campagna | Etichette degli ID campagna |
| ID consegna | ID di tutte le consegne per le quali i KPI sono stati inviati durante la durata. Sono inclusi anche gli ID delle consegne principali di consegna periodica e consegna transazione. Esempio: È stata pianificata una consegna periodica DM1 e DM2, DM3, DM4 e DM5 sono state consegne figlie della consegna periodica.  L'ID consegna visualizza i risultati per tutte le consegne, da DM1 a DM5. |
| Etichetta consegna | Etichette ID consegna |
| ID consegna eseguito | ID delle sole consegne eseguite. Nessun ID della consegna master ricorrente/transazionale. Esempio: È stata pianificata una consegna periodica DM1 e DM2, DM3, DM4 e DM5 sono state consegne figlie della consegna periodica. L'ID consegna eseguito visualizza i risultati per tutte le consegne che iniziano da DM2 a DM5, le consegne effettivamente eseguite. |
| Etichetta consegna eseguita | Etichette di ID di consegna eseguiti |
