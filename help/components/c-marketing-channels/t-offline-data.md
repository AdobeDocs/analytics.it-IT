---
description: Aggiunta di dati offline ai rapporti del canale di marketing.
seo-description: Aggiunta di dati offline ai rapporti del canale di marketing.
seo-title: Aggiungere dati offline
solution: Analytics
subtopic: Canali di marketing
title: Aggiungere dati offline
topic: Reports and Analytics
uuid: bbf4661a-b6b1-4a89-a3cf-ae8dd785d37d
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Aggiungere dati offline

Aggiunta di dati offline ai rapporti del canale di marketing.

Canali online ti permettono di classificare i dati per i visitatori provenienti da fonti come un motore di ricerca, un annuncio su Internet, un dominio di provenienza o una campagna e-mail. I canali offline si applicano ai visitatori che hanno trovato il tuo sito tramite annunci televisivi, giornali o annunci pubblicitari di riviste.

**Integrare le origini dati nei rapporti del canale di marketing**

Se desiderate integrare i dati [di origine](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_faq.html) dati nei rapporti del canale di marketing, tenete presente quanto segue:

* Eventuali hit standard passati ai report di analisi con un [transactionID](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_Transaction_ID.html) vengono elaborati normalmente attraverso le regole di elaborazione dei canali di marketing.
* Qualsiasi origine `transactionID` dati passata in analisi viene automaticamente associata allo stesso canale di marketing su cui è stato elaborato l'hit standard.
* Qualsiasi altro dato di origine dati non passa attraverso le regole di elaborazione dei canali di marketing.

Per ulteriori informazioni sulle origini dati, consulta la guida [Origini](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html) dati.

Per classificare i dati dei canali offline, attiva i dati in Origini dati, quindi scarica e modifica il modello.

Vedere "Uso delle origini dati" nella Guida [utente di](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)Origini dati.

**Aggiungere dati offline**

1. Clic **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. Nella pagina Origini dati fai clic su **[!UICONTROL Create.]**
1. In **[!UICONTROL 1. Select Category]**, selezionare **[!UICONTROL Offline Channel Data]**.
1. In **[!UICONTROL 2. Select Type]**, selezionare **[!UICONTROL Offline Channel Data]**.
1. Fai clic su **[!UICONTROL Activate.]**
1. Mappate le metriche offline alle metriche di reporting seguendo i prompt nella procedura guidata Attivazione origine dati.
1. Scaricate e modificate il file modello in un editor, ad esempio Excel.

   Vedere "Creazione di un file Origini dati" nella Guida [utente di](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)Origini dati.

1. Carica il file come descritto in "Caricamento di un file Origini dati" nella Guida [utente di](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)Origini dati.
