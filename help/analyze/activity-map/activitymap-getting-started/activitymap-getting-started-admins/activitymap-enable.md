---
description: Spiega i passaggi necessari per l'amministratore di Analytics per abilitare la raccolta di collegamenti [!DNL Activity Map] e il download degli utenti.
seo-description: Spiega i passaggi necessari per l'amministratore di Analytics per abilitare la raccolta di collegamenti [!DNL Activity Map] e il download degli utenti.
seo-title: Abilita [!DNL Activity Map]
solution: Analytics
title: Abilita [!DNL Activity Map]
topic: Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# Abilita [!DNL Activity Map]{#enable-activity-map}

Spiega i passaggi necessari per l'amministratore di Analytics per abilitare la raccolta [!DNL Activity Map] dei collegamenti e il download degli utenti.

## Passaggio 1: Aggiorna il codice AppMeasurement (Javascript) a v1.6 (o versione successiva) {#section_5D1586289DF2489289B1B6C1C80C300D}

Il [!DNL Activity Map] modulo fa parte del file AppMeasurement.js (nella parte superiore del file). La libreria AppMeasurement caricherà il modulo al momento della creazione dell'istanza. [!DNL Activity Map]

[!DNL Activity Map] i dati possono essere raccolti solo se ti aggiorni a questa versione (o successiva) di AppMeasurement.

1. Scarica il codice AppMeasurement più recente (AppMeasurement_Javascript-1.6.zip) andando a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** e [implementalo](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Abbiamo incluso alcuni [esempi di codice](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) di implementazione per aiutarti a visualizzare le modifiche apportate al codice includendo il [!DNL Activity Map] modulo.

1. Convalida l’implementazione:

   1. Quando si fa clic su un elemento selezionabile, i dati vengono memorizzati in un cookie denominato s_sq.
   1. I [!DNL Activity Map] dati possono essere visualizzati nella stringa di query nella chiamata di tracciamento. Ad esempio:

      ```
      …&c.&a.&[!DNL Activity Map].&link=My%20Link&region=My%20Region&page=My%20Page&.[!DNL Activity Map]&.a&.c&...
      ```

1. Per visualizzare il collegamento o la regione della pagina, suddividi questo rapporto per **[!UICONTROL[!DNL Activity Map]Link by Region]** :  ![](assets/am_breakdown.png){width="400px"}

## Passaggio 2: Abilita [!DNL Activity Map] rapporti {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Innanzitutto, è necessario abilitare [!DNL Activity Map] i rapporti a livello di suite di rapporti.

1. Accedi ad Adobe Analytics e passa a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Suite di rapporti &gt;[seleziona suite]di rapporti &gt; Modifica impostazioni &gt;[!DNL Activity Map]]** &gt; **[!UICONTROL[!DNL Activity Map]Reporting]** .
1. [!DNL Activity Map] raccoglie i dati del collegamento nei [!DNL Activity Map] rapporti. Per attivare l'attivazione, è prima necessario attivare le variabili facendo clic su **[!UICONTROL Abilita[!DNL Activity Map]rapporti]**.

   Questo passaggio aggiunge tutte le dimensioni di Analytics necessarie per la raccolta dei dati.

1. Dopo circa un'ora, controllate il rapporto [sulla pagina](/help/analyze/activity-map/activitymap-reporting-analytics.md)[!DNL Activity Map], che mostra tutte le pagine in cui gli utenti hanno fatto clic su un collegamento.

## Passaggio 3: Aggiunta di utenti al gruppo di [!DNL Activity Map] accesso {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Fai clic su **[!UICONTROL Add Users to Group]**.

   Viene visualizzata la pagina Gestione dei gruppi in Admin Console.

1. [Aggiungete utenti a questo gruppo](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) e **[!UICONTROL Save Group]**.

1. Questo consente agli utenti Admin di scaricare [!DNL Activity Map] da **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  Se desiderate che gli utenti non amministratori scarichino [!DNL Activity Map], dovete creare un nuovo gruppo di utenti che fornisca l'autorizzazione a <span class="uicontrol"> Strumenti </span> &gt; Installazione legacy di <span class="uicontrol"> ClickMap </span>. Potete quindi aggiungere utenti non amministratori a questo gruppo. Questo livello di autorizzazione, unito alla mappa attività [!DNL] Access, fornirà autorizzazioni complete per scaricare e utilizzare lo strumento. 
</note>
