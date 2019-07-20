---
description: Illustra i passaggi necessari all'amministratore di Analytics per abilitare la raccolta di collegamenti Mappa dell'attività e il download degli utenti.
seo-description: Illustra i passaggi necessari all'amministratore di Analytics per abilitare la raccolta di collegamenti Mappa dell'attività e il download degli utenti.
seo-title: Abilitare la mappa dell'attività
solution: Analytics
title: Abilitare la mappa dell'attività
topic: Activity map
uuid: 30433319-d 0 e 6-4977-951 a -4492 b 356 e 1 f 2
translation-type: tm+mt
source-git-commit: 8f72f8cf086be0eade5616b074123a9f22e33347

---


# Enable Activity Map{#enable-activity-map}

Illustra i passaggi necessari all'amministratore di Analytics per abilitare la raccolta di collegamenti Mappa dell'attività e il download degli utenti.

## Passaggio 1: Update Your AppMeasurement (Javascript) Code to v1.6 (or higher) {#section_5D1586289DF2489289B1B6C1C80C300D}

Il modulo Activity Map (Mappa attività) fa parte del file appmeasurement. js (posizionato nella parte superiore del file). La libreria appmeasurement caricherà il modulo Activity Map quando create un'istanza.

I dati delle mappe dell'attività non possono essere raccolti a meno che non effettuiate l'aggiornamento a questa versione (o versione successiva) di appmeasurement.

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   We have included some [sample implementation code](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) to help you visualize the changes that have been made to the code by including the Activity Map module.

1. Convalida l’implementazione:

   1. Quando si fa clic su un elemento cliccabile, i dati saranno memorizzati in un cookie denominato s_ sq.
   1. I dati Activity Map sono visibili nella stringa query sulla chiamata di tracciamento. Ad esempio:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## Passaggio 2: Enable Activity Map reports {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Innanzitutto, è necessario abilitare i rapporti Activity Map a livello di suite di rapporti.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt; Activity Map]** &gt; **[!UICONTROL Activity Map Reporting]** .
1. Activity Map raccoglie i dati del collegamento nei report Activity Map. For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable Activity Map Reports]**.

   Questo passaggio aggiunge tutte le dimensioni di Analytics necessarie per raccogliere i dati.

1. After about an hour, check the [Activity Map Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), which shows all the pages where users clicked on a link.

## Passaggio 3: Add users to Activity Map access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Fai clic su **[!UICONTROL Add Users to Group]**.

   Verrà visualizzata la pagina di gestione dei gruppi in Admin Console.

1. [Aggiungete utenti a questo gruppo](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) e **[!UICONTROL Save Group]**.

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  If you want Non-Admin users to download Activity Map, you need to create a new user group that provides permission to 
 <span class="uicontrol"> Tools </span> &gt; 
 <span class="uicontrol"> Legacy ClickMap Installation </span>. Puoi quindi aggiungere utenti non amministratori a questo gruppo. Questo livello di autorizzazione combinato con Accesso mappa dell'attività fornirà le autorizzazioni complete per scaricare e utilizzare lo strumento. 
</note>
