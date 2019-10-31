---
description: Spiega i passaggi necessari per l'amministratore di Analytics per abilitare la raccolta di collegamenti Activity Map e il download degli utenti.
seo-description: Spiega i passaggi necessari per l'amministratore di Analytics per abilitare la raccolta di collegamenti Activity Map e il download degli utenti.
seo-title: Abilitare Activity Map
solution: Analytics
title: Abilitare Activity Map
topic: Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 38eb2298a2fc351591542bdfac9016ce4497c484

---


# Abilitare Activity Map{#enable-activity-map}

Spiega i passaggi necessari per l'amministratore di Analytics per abilitare la raccolta di collegamenti Activity Map e il download degli utenti.

## Passaggio 1: Aggiorna il codice AppMeasurement (Javascript) a v1.6 (o versione successiva) {#section_5D1586289DF2489289B1B6C1C80C300D}

Il modulo Activity Map fa parte del file AppMeasurement.js (nella parte superiore del file). La libreria AppMeasurement caricherà il modulo Activity Map al momento della creazione dell'istanza.

I dati della Activity Map non possono essere raccolti se non si esegue l'aggiornamento a questa versione (o successiva) di AppMeasurement.

1. Scarica il codice AppMeasurement più recente (AppMeasurement_Javascript-1.6.zip) andando a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** e [implementalo](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Abbiamo incluso alcuni [esempi di codice](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) di implementazione per aiutarti a visualizzare le modifiche apportate al codice includendo il modulo Activity Map.

1. Convalida l’implementazione:

   1. Quando si fa clic su un elemento selezionabile, i dati vengono memorizzati in un cookie denominato s_sq.
   1. I dati della Activity Map sono visibili nella stringa query nella chiamata di tracciamento. Ad esempio:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Per visualizzare il collegamento o la regione **[!UICONTROL Activity Map Link by Region]** della pagina, suddividi il rapporto per:  ![](assets/am_breakdown.png){width="400px"}

## Passaggio 2: Attivare i rapporti Activity Map {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Innanzitutto, è necessario abilitare i rapporti Activity Map a livello di suite per report.

1. Accedi ad Adobe Analytics e passa a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Suite di rapporti &gt;[seleziona suite]di rapporti &gt; Modifica impostazioni &gt; Activity Map]** &gt; **[!UICONTROL Activity Map Reporting]** .
1. Activity Map raccoglie i dati del collegamento nei rapporti Activity Map. Per attivare l’attivazione, è innanzitutto necessario attivare le variabili facendo clic su **[!UICONTROL Enable Activity Map Reports]**.

   Questo passaggio aggiunge tutte le dimensioni di Analytics necessarie per la raccolta dei dati.

1. Dopo circa un'ora, controllate il rapporto [della pagina Mappa](/help/analyze/activity-map/activitymap-reporting-analytics.md)attività, che mostra tutte le pagine in cui gli utenti hanno fatto clic su un collegamento.

## Passaggio 3: Aggiunta di utenti al gruppo di accesso Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Fai clic su **[!UICONTROL Add Users to Group]**.

   Viene visualizzata la pagina Gestione dei gruppi in Admin Console.

1. [Aggiungete utenti a questo gruppo](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) e **[!UICONTROL Save Group]**.

1. Questo consente agli utenti Admin di scaricare la Activity Map da **Adobe Analytics** &gt; **[!UICONTROL Tools]** &gt; **ActivityMap** .

> [!NOTE] Se desiderate che gli utenti non amministratori scarichino la Activity Map, create un nuovo gruppo di utenti che fornisca l'autorizzazione "Strumenti" e "Installazione legacy ClickMap". Questo livello di autorizzazione combinato con l'accesso alla Activity Map fornisce le autorizzazioni per scaricare e utilizzare lo strumento.
