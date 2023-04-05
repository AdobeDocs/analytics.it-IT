---
description: Spiega i passaggi che l’amministratore di Analytics deve completare per abilitare la raccolta di collegamenti Activity Map e il download degli utenti.
title: Abilitare Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: 87c2f559990674ee738e1ad57166cf192d58232c
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 6%

---

# Abilitare Activity Map{#enable-activity-map}

Spiega i passaggi che l’amministratore di Analytics deve completare per abilitare la raccolta di collegamenti Activity Map e il download degli utenti.

## Passaggio 1. Aggiorna il codice di implementazione {#section_5D1586289DF2489289B1B6C1C80C300D}

Il modulo Activity Map fa parte di AppMeasurement.js e dell’SDK per web (versione 2.15.0 o successiva).
La libreria AppMeasurement o l&#39;SDK per web caricherà il modulo Activity Map quando viene creata un&#39;istanza.

>[!NOTE]
>
>I dati di Activity Map non possono essere raccolti a meno che non si esegua l’aggiornamento a **AppMeasurement** **versione 1.6** o superiore o **SDK per web** **versione 2.15.0** o superiore


1. Scarica la libreria JavaScript più recente a seconda che utilizzi AppMeasurement o SDK web.

   - **AppMeasurement** codice (AppMeasurement_Javascript-1.6.zip) andando a  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Code manager]** e [implementare](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=it).

      Ne abbiamo inclusi alcuni [codice di implementazione di esempio](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) per visualizzare le modifiche apportate al codice includendo il modulo Activity Map.

   - **SDK per web** code (alloy.js). Vedi [Installa l&#39;SDK - Opzione 2: Installazione della versione autonoma predefinita](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) per ulteriori informazioni. Assicurati di utilizzare la versione 2.15 o successiva.

      Vedi [Tracciare i collegamenti](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) per informazioni su come implementare il tracciamento dei collegamenti e come abilitare la mappatura attività acquisendo il `region` dell’elemento HTML selezionato.

      >[!NOTE]
      >
      >L&#39;abilitazione del tracciamento dei collegamenti con SDK per web invia attualmente eventi di collegamento quando un cliente passa da una pagina all&#39;altra. Questo è diverso dal funzionamento di AppMeasurement e può potenzialmente causare hit fatturabili aggiuntivi inviati ad Adobe.


1. Confermare l’implementazione:

   1. Quando fai clic su un elemento selezionabile, i dati vengono memorizzati in un cookie denominato s_sq.
   1. I dati di Activity Map possono essere visualizzati nella stringa query nella chiamata di tracciamento. Ad esempio:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Suddividi report per **[!UICONTROL Activity Map Link by Region]** per visualizzare il collegamento o l’area geografica della pagina:  ![](assets/am_breakdown.png){width="400px"}

## Passaggio 2. Abilitare i rapporti di Activity Map {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Innanzitutto, devi abilitare i rapporti di Activity Map a livello di suite di rapporti.

1. Accedi ad Adobe Analytics e passa a  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. Activity Map raccoglie i dati del collegamento nei rapporti di Activity Map. Affinché l’attivazione avvenga, devi prima attivare le variabili facendo clic su **[!UICONTROL Enable Activity Map Reports]**.

   Questo passaggio aggiunge tutte le dimensioni di Analytics necessarie per raccogliere i dati.

1. Dopo circa un&#39;ora, controlla il [Rapporto pagina Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), che mostra tutte le pagine in cui gli utenti hanno fatto clic su un collegamento.

## Passaggio 3. Aggiungere utenti al gruppo di accesso di Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Fai clic su **[!UICONTROL Add Users to Group]** (Usa modello di attribuzione non predefinito).

   Viene visualizzata la pagina di gestione dei gruppi nell’Admin Console.

1. [Aggiungi utenti a questo gruppo](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=it) e **[!UICONTROL Save Group]**.

1. In questo modo gli utenti amministratori possono scaricare Activity Map da  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

>[!NOTE]
>
>Se desideri che gli utenti non amministratori scarichino Activity Map, crea un nuovo gruppo di utenti che fornisca l’autorizzazione &quot;Strumenti&quot; e &quot;Installazione ClickMap legacy&quot;. Questo livello di autorizzazione combinato con Activity Map Access fornisce le autorizzazioni per scaricare e utilizzare lo strumento.
