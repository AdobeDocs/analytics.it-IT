---
description: Descrive i passaggi che l’amministratore di Analytics deve completare per abilitare la raccolta di collegamenti Activity Map e il download degli utenti.
title: Abilitare Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: ae1c2ff1987e2fe5d147bfe74874b53492d48b5e
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 11%

---


# Attivare e abilitare Activity Map

Descrive i passaggi che l’amministratore di Analytics deve completare per abilitare la raccolta di collegamenti Activity Map e il download degli utenti.

## Passaggio 1. Attiva Activity Map {#update_code}

Il modulo Activity Map fa parte di AppMeasurement.js, dei tag Adobe Experience Platform e del Web SDK (alloy.js). I dati Activity Map non possono essere raccolti a meno che tu non aggiorni a **Web SDK versione 2.15.0** o superiore, oppure **Estensione tag Adobe Analytics v1.90** o superiore, oppure **AppMeasurement versione 1.6** o superiore.

+++Web SDK (estensione tag Adobe Experience Platform)

1. Nei tag di Adobe Experience Platform, passa alla proprietà per la quale stai implementando Analytics. Sotto [!UICONTROL Extensions] -> [!UICONTROL Adobe Experience Platform Web SDK], seleziona **[!UICONTROL Enable click data collection]** come evidenziato di seguito.
1. Crea la libreria con le modifiche.
1. Pubblica la libreria in produzione.

![](assets/web_sdk.png)

**Convalida**

Interagisci con le chiamate tramite la scheda Rete di Developer Console:

1. Carica lo script Development Launch sul sito.
1. Al clic degli elementi, cerca &#39;/ee&#39; nella scheda Rete

   ![](assets/validation1.png)

Adobe Experience Platform Debugger:

1. Scarica e installa [Adobe Experience Platform Debugger](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Vai a [!UICONTROL Logs] > [!UICONTROL Edge] > [!UICONTROL Connect to Edge].

   ![](assets/validation2.jpg)

**Domande frequenti**

* **La chiamata di interazione non viene attivata nella scheda Rete.**
La raccolta dati di clic in una chiamata di raccolta, è necessario filtrare con &quot;/ee&quot; o &quot;collect?&quot;

* **Non esiste alcuna visualizzazione del payload per la chiamata di raccolta.**
La chiamata di raccolta è progettata in modo tale che il tracciamento non influisca sulla navigazione verso altri siti, pertanto la funzione di scaricamento del documento è applicabile alle chiamate di raccolta. Questo non influisce sulla raccolta di dati, ma se devi convalidare su pagina, aggiungi target = &quot;_blank&quot; al rispettivo elemento. Il collegamento viene quindi aperto in una nuova scheda.

* **Come posso ignorare la raccolta di dati PII?**
Aggiungi le rispettive condizioni in&lt;&lt; su prima del collegamento, fai clic su send callback>> e restituisce false per ignorare tali valori. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it)

  Codice di esempio:

  ![](assets/sample-code.png)

+++

+++Implementazione manuale di Web SDK

Consulta [Tracciare i collegamenti](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=it) per informazioni su come implementare il tracciamento dei collegamenti e come abilitare l’Activity Map acquisendo `region` dell’elemento HTML selezionato.

>[!NOTE]
>
>L’abilitazione del tracciamento dei collegamenti con l’SDK per web attualmente invia eventi di collegamento quando un cliente passa da una pagina all’altra. Questo è diverso dal funzionamento di AppMeasurement e può potenzialmente causare hit fatturabili aggiuntivi inviati ad Adobe.

+++

Estensione +++Analytics (tag Adobe Experience Platform)

Nei tag di Adobe Experience Platform, passa alla proprietà per la quale stai implementando Analytics. In [!UICONTROL Install Extension] finestra di dialogo, seleziona **[!UICONTROL Use Activity Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. Scarica la libreria JavaScript più recente, ad AppMeasurement.
Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Code manager]**.
1. Implementalo seguendo le istruzioni [queste istruzioni](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=it).

+++

## Passaggio 2. Abilitare i rapporti di Activity Map {#enable}

Devi abilitare i rapporti Activity Map a livello di suite di rapporti.

1. Accedi ad Adobe Analytics e passa a  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]** .

1. Activity Map raccoglie i dati dei collegamenti nei rapporti Activity Map. Affinché l&#39;attivazione avvenga, devi prima attivare le variabili facendo clic su **[!UICONTROL Enable Activity Map Reports]**.

   Questo passaggio aggiunge tutte le dimensioni di Analytics necessarie per raccogliere i dati.

   ![](assets/enable.png)

1. Dopo circa un&#39;ora, controllare [Report pagina Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), che mostra tutte le pagine in cui gli utenti hanno fatto clic su un collegamento.

## Passaggio 3. Aggiungi utenti a [!UICONTROL Activity Map Access] profilo prodotto {#add_users}

1. Fai clic su **[!UICONTROL Add Users to Group]** (Usa modello di attribuzione non predefinito).

   Verrà visualizzata la pagina del profilo prodotto in [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. Se non hai creato un’ [!UICONTROL Activity Map Access] profilo di prodotto, procedi ora. Gli elementi di autorizzazione richiesti per questo profilo sono [!UICONTROL Analytics Tools] > [!UICONTROL Activity Map] e [!UICONTROL Analytics Tools] > [!UICONTROL Segment Publishing].

1. Aggiungi utenti a quel profilo di prodotto. Questo consente agli utenti di scaricare Activity Map da  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

