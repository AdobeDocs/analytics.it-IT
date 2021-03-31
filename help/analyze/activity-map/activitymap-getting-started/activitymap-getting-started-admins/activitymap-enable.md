---
description: Spiega i passaggi che l’amministratore di Analytics deve completare per abilitare la raccolta di collegamenti Activity Map e il download degli utenti.
title: Abilitare Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 9%

---


# Abilitare Activity Map{#enable-activity-map}

Spiega i passaggi che l’amministratore di Analytics deve completare per abilitare la raccolta di collegamenti Activity Map e il download degli utenti.

## Passaggio 1: Aggiorna il codice AppMeasurement (Javascript) alla versione 1.6 (o successiva) {#section_5D1586289DF2489289B1B6C1C80C300D}

Il modulo Activity Map fa parte del file AppMeasurement.js (che si trova nella parte superiore del file). La libreria AppMeasurement carica il modulo Activity Map quando viene creata un&#39;istanza.

I dati di Activity Map possono essere raccolti solo se si esegue l’aggiornamento a questa versione (o superiore) di AppMeasurement.

1. Scarica il codice AppMeasurement più recente (AppMeasurement_Javascript-1.6.zip) andando su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Code Manager]** e [implementalo](https://docs.adobe.com/content/help/it-IT/analytics/implementation/js/overview.html).

   Abbiamo incluso alcuni [codici di implementazione di esempio](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) per aiutarti a visualizzare le modifiche apportate al codice includendo il modulo Activity Map.

1. Confermare l’implementazione:

   1. Quando fai clic su un elemento selezionabile, i dati vengono memorizzati in un cookie denominato s_sq.
   1. I dati di Activity Map possono essere visualizzati nella stringa query nella chiamata di tracciamento. Ad esempio:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Per visualizzare il collegamento o l’area geografica della pagina, suddividi questo rapporto per **[!UICONTROL Activity Map Link by Region]**:  ![](assets/am_breakdown.png){width=&quot;400px&quot;}

## Passaggio 2: Abilitare i rapporti di Activity Map {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Innanzitutto, devi abilitare i rapporti di Activity Map a livello di suite di rapporti.

1. Accedi a Adobe Analytics e passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. Activity Map raccoglie i dati del collegamento nei rapporti di Activity Map. Affinché l’attivazione avvenga, è necessario attivare prima le variabili facendo clic su **[!UICONTROL Enable Activity Map Reports]**.

   Questo passaggio aggiunge tutte le dimensioni di Analytics necessarie per raccogliere i dati.

1. Dopo circa un&#39;ora, controlla il [report pagina Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), che mostra tutte le pagine in cui gli utenti hanno fatto clic su un collegamento.

## Passaggio 3: Aggiungi utenti al gruppo di accesso Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Fai clic su **[!UICONTROL Add Users to Group]**.

   Viene visualizzata la pagina di gestione dei gruppi nell’Admin Console.

1. [Aggiungi gli utenti a questo ](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=it-IT) gruppo  **[!UICONTROL Save Group]**.

1. Questo consente agli utenti amministratori di scaricare Activity Map da **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

>[!NOTE]
>
>Se desideri che gli utenti non amministratori scarichino Activity Map, crea un nuovo gruppo di utenti che fornisca l’autorizzazione &quot;Strumenti&quot; e &quot;Installazione ClickMap legacy&quot;. Questo livello di autorizzazione combinato con Activity Map Access fornisce le autorizzazioni per scaricare e utilizzare lo strumento.
