---
description: Aggiungi dati offline ai rapporti Canale di marketing.
seo-description: Aggiungi dati offline ai rapporti Canale di marketing.
seo-title: Aggiungere dati offline
solution: Analytics
subtopic: Canali di marketing
title: Aggiungere dati offline
topic: Reports & Analytics
uuid: bbf 4661 a-b 6 b 1-4 a 89-a 3 cf-ae 8 dd 785 d 37 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Aggiungere dati offline

Aggiungi dati offline ai rapporti Canale di marketing.

I canali online consentono di classificare i dati per i visitatori che arrivano attraverso fonti come un motore di ricerca, un annuncio Internet, un dominio di riferimento o una campagna e-mail. I canali offline si applicano ai visitatori che hanno trovato il tuo sito tramite annunci televisivi, quotidiani o annunci pubblicitari delle riviste.

**Integrare le origini dati nei rapporti sul canale di marketing**

If you want to integrate [data sourced data](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_faq) into Marketing Channel reports, keep in mind the following:

* Any standard hits passed in to analytics reports with a [transactionID](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_Transaction_ID) are processed through marketing channel processing rules as normal.
* Any `transactionID` data sources passed into analytics are automatically associate with the same marketing channel on which the standard hit was processed.
* Tutti gli altri dati acquisiti non passano attraverso le regole di elaborazione del canale di marketing.

See [Data Sources](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html) help for more information about Data Sources.

Per classificare i dati del canale offline, attiva i dati in Origini dati, quindi scarica e modifica il modello.

See "Working with Data Sources" in the [Data Sources User Guide](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).

**Aggiungere dati offline**

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. On the Data Sources page, click **[!UICONTROL Create.]**
1. Under **[!UICONTROL 1. Select Category]**, select **[!UICONTROL Offline Channel Data]**.
1. Under **[!UICONTROL 2. Select Type]**, select **[!UICONTROL Offline Channel Data]**.
1. Fai clic su **[!UICONTROL Activate.]**
1. Mappatura delle metriche offline alle metriche di reporting seguendo i prompt nella procedura guidata Attivazione origine dati.
1. Scaricate e modificate il file modello in un editor, ad esempio Excel.

   See "Creating a Data Sources File" in the [Data Sources User Guide](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).

1. Upload the file as described in "Uploading a Data Sources File" in the [Data Sources User Guide](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).
