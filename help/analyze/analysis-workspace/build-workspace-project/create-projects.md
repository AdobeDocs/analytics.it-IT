---
description: Scopri le nozioni di base sulla creazione di un progetto in Analysis Workspace
title: Creare progetti
feature: Workspace Basics
role: User, Admin
exl-id: 6130b1d8-078c-46d8-9fce-eb39739a9570
source-git-commit: fabe043264e4567d54dc497897fff0aaad77eaaf
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 14%

---

# Creare progetti in Analysis Workspace

[Progetti](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace consente di visualizzare le analisi business-critical che possono essere condivise con le parti interessate all’interno o all’esterno dell’organizzazione.

Per informazioni generali su come iniziare a utilizzare Analysis Workspace, consulta [Panoramica di Analysis Workspace](/help/analyze/analysis-workspace/home.md).

Le sezioni seguenti descrivono come creare un progetto e iniziare ad aggiungere i blocchi predefiniti chiave per qualsiasi progetto Analysis Workspace: pannelli, visualizzazioni e componenti.

## Creare un progetto da un progetto o da un rapporto vuoto

1. In Adobe Analytics, seleziona [!UICONTROL **Workspace**].

1. Scegli se creare un progetto vuoto o un progetto da un rapporto:

   +++Crea un progetto vuoto

   1. Il giorno [!UICONTROL **Workspace**] , seleziona la scheda [!UICONTROL **Progetti**] sul lato sinistro della pagina, quindi seleziona [!UICONTROL **Crea progetto**].

   1. Scegli se creare un progetto vuoto o una scheda di valutazione mobile vuota

      * **Progetto vuoto** se prevedi di condividere l’analisi dal browser
      * [**Scorecard per dispositivi mobili vuota**](/help/analyze/mobile-app/curator.md) se prevedi di condividere l’analisi dall’app mobile Adobe Analytics dashboards.

   1. Seleziona [!UICONTROL **Crea**].

+++

   +++Creare un progetto da un rapporto

   1. Il giorno [!UICONTROL **Workspace**] , seleziona la scheda [!UICONTROL **Rapporti**] sul lato sinistro della pagina.

   1. Cerca o accedi al report che desideri utilizzare, quindi selezionalo quando viene visualizzato.

      Per impostazione predefinita, è disponibile una serie di rapporti standard. Inoltre, la tua organizzazione potrebbe aver creato rapporti personalizzati tra cui scegliere.

   1. Seleziona [!UICONTROL **Progetto**] > [!UICONTROL **Salva**] per salvare il report come nuovo progetto.

      Per ulteriori informazioni sui rapporti, consulta &quot;Navigare nella scheda Rapporti&quot; in [Pagina di destinazione di Adobe Analytics](/help/analyze/landing.md).

+++

1. Successivamente, devi aggiungere pannelli, visualizzazioni e componenti al progetto. Innanzitutto, aggiungi i pannelli al progetto in Analysis Workspace, come descritto in [Aggiungere pannelli al progetto](#add-panels-to-the-project). Puoi quindi aggiungere visualizzazioni a qualsiasi pannello. Infine, puoi aggiungere componenti a qualsiasi pannello o visualizzazione.

## Aggiungere pannelli al progetto {#panels}

[Pannelli](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it) sono alla base di qualsiasi progetto in Analysis Workspace. I pannelli vengono utilizzati per organizzare il contenuto (visualizzazioni e componenti) di un progetto.

Molti dei pannelli forniti in Analysis Workspace generano una serie completa di analisi basate su alcuni input dell’utente.

Per aggiungere un pannello:

1. Seleziona la [!UICONTROL **Pannelli**] nella barra a sinistra.

   ![](assets/build-panels.png)

1. Cerca il pannello da aggiungere. Quando viene visualizzato nella barra a sinistra, trascinalo nel progetto.

1. Aggiungere visualizzazioni al pannello, come descritto in [Aggiungere visualizzazioni al progetto](#add-visualizations-to-the-project).

   In alternativa, è possibile aggiungere componenti direttamente a un pannello, come descritto in [Aggiungere componenti al progetto](#add-components-to-the-project).

## Aggiungere visualizzazioni al progetto

[Visualizzare](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=it) (ad esempio, una tabella a forma libera, un grafico a barre o un grafico a linee) possono essere utilizzati per riprodurre visivamente i dati.

>[!TIP]
>
>Le tabelle a forma libera sono il tipo di visualizzazione più comune e costituiscono la base per l’analisi interattiva dei dati. Per ulteriori dettagli sull’utilizzo delle tabelle a forma libera in Analysis Workspace, consulta [Tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

Per aggiungere una visualizzazione:

1. Seleziona la **[!UICONTROL Visualizations]** nella barra a sinistra.

   ![](assets/build-visualizations.png)

1. Cerca la visualizzazione da aggiungere. Quando viene visualizzato nella barra a sinistra, trascinalo su un pannello all’interno del progetto.

1. Aggiungi componenti alla visualizzazione, come descritto in [Aggiungere componenti al progetto](#add-components-to-the-project).

## Aggiungere componenti al progetto

[Componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) costituisce i dati effettivi di qualsiasi progetto. Puoi aggiungere componenti alle visualizzazioni o ai pannelli.

>[!TIP]
>
>Per informazioni su ciascun componente, seleziona l’icona Informazioni accanto al nome di un componente nella barra a sinistra, oppure vedi [Guida ai componenti di Analytics](/help/components/home.md).

Per aggiungere un componente:

1. Seleziona la **[!UICONTROL Components]** nella barra a sinistra.

   ![](assets/build-components.png)

1. Cerca il componente che desideri aggiungere. Quando viene visualizzato nella barra a sinistra, trascinalo su un pannello o una visualizzazione all’interno del progetto.

1. Condividi il progetto come descritto in (facoltativo) [Salvare e condividere il progetto](#save-and-share-the-project).

## Salvare e condividere il progetto

Quando crei un’analisi in Analysis Workspace, il lavoro viene [salvato automaticamente](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

Una volta completato il progetto e questo sta raccogliendo approfondimenti utili, il progetto è pronto per essere utilizzato da altri utenti. Puoi condividere il progetto con utenti e gruppi dell’organizzazione o anche con persone esterne a questa. Per informazioni sulla condivisione di un progetto, consulta [Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md).
