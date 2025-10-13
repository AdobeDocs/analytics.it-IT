---
title: Guida introduttiva ad Activity Map
description: Inizia a utilizzare le dimensioni e la sovrapposizione di Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Guida introduttiva ad Activity Map

Activity Map in Adobe Analytics comprende quattro elementi principali:

* **Impostazione suite di rapporti**: devi abilitare Activity Map nelle impostazioni della suite di rapporti. Quando è abilitata, la suite di rapporti crea diverse variabili riservate per le dimensioni e le metriche di Activity Map.
* **Implementazione**: raccogli i dati di Activity Map sul tuo sito Web o sulla tua proprietà. La personalizzazione delle modalità di raccolta dei dati può migliorare la qualità e l’esperienza dei rapporti.
* **Dimensioni e metriche di Workspace**: se l&#39;implementazione è configurata correttamente, puoi utilizzare le dimensioni e le metriche di Activity Map in Analysis Workspace.
* **Sovrapposizione**: Adobe offre un&#39;estensione del browser per visualizzare i dati di Activity Map nel contesto del sito Web.

## Abilita impostazione suite di rapporti

Per poter iniziare a raccogliere i dati, la funzione di reporting di Activity Map deve essere abilitata in una suite di rapporti. Se la tua implementazione invia i dati di Activity Map a una suite di rapporti senza che sia abilitato il reporting di Activity Map, i dati di Activity Map non vengono inclusi nell’hit.

**[!UICONTROL Admin]** > **[!UICONTROL Report suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map reporting]** > **[!UICONTROL Enable Activity Map Reports]**

L’abilitazione dei rapporti di Activity Map crea diverse variabili riservate di back-end. Per ulteriori informazioni, consulta [Rapporti di Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) nella guida per l&#39;amministratore di Adobe Analytics.

## Installazione del codice

L’implementazione deve essere configurata correttamente per inviare dati di Activity Map ad Adobe.

+++Estensione tag Web SDK

La raccolta dati di Activity Map richiede l&#39;estensione **[!UICONTROL Adobe Experience Platform Web SDK]** v2.23 o successiva. Le versioni di estensione fino alla versione v2.16 dispongono di supporto limitato. Queste versioni precedenti dell’estensione inviano i dati di Activity Map in un evento separato dal resto dei dati. Questo evento aggiuntivo aumenta il numero di hit inviati ad Adobe Analytics o Adobe Experience Platform.

L&#39;impostazione di configurazione **[!UICONTROL Click data collection]** gestisce la raccolta dati di Activity Map ed è in genere abilitata per impostazione predefinita. Puoi verificare che sia abilitato nelle impostazioni di configurazione dell&#39;estensione:

1. Accedi a [experience.adobe.com](https://experience.adobe.com)
1. Seleziona **[!UICONTROL Data Collection]** nel menu di accesso rapido o il selettore di prodotto in alto a destra.
1. Selezionare **[!UICONTROL Tags]** nel menu di navigazione a sinistra.
1. Seleziona il tag desiderato da modificare.
1. Selezionare **[!UICONTROL Extensions]** nel menu di navigazione a sinistra.
1. Selezionare **[!UICONTROL Adobe Experience Platform Web SDK]** nell&#39;elenco delle estensioni installate, quindi selezionare **[!UICONTROL Configure]** a destra.
1. Individuare la sezione con etichetta [!UICONTROL Data Collection] e verificare che la casella di controllo **[!UICONTROL Enable click data collection]** sia abilitata.
1. Seleziona **[!UICONTROL Save]**.
1. Se necessario, crea le modifiche in una libreria e pubblicale in produzione.

Per ulteriori informazioni, vedere [Configurare l&#39;estensione tag Web SDK](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection).

+++

+++Libreria JavaScript Web SDK (`alloy.js`)

La raccolta dati di Activity Map richiede la libreria Web SDK JavaScript v2.20 o successiva. Le versioni della libreria fino alla versione v2.15 sono supportate in modo limitato. Queste versioni precedenti della libreria inviano i dati di Activity Map in un evento separato dal resto dei dati. Questo evento aggiuntivo aumenta il numero di hit inviati ad Adobe Analytics o Adobe Experience Platform.

La variabile di configurazione del Web SDK [`clickCollectionEnabled`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) gestisce la raccolta automatica dei dati di Activity Map. È abilitato per impostazione predefinita, a meno che non sia esplicitamente disabilitato.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Estensione tag Adobe Analytics

L&#39;impostazione di configurazione **[!UICONTROL Use Activity Map]** gestisce la raccolta dati di Activity Map ed è in genere abilitata per impostazione predefinita. È disponibile per tutte le estensioni tag versione 1.9.0 o successiva. Puoi verificare che sia abilitato nelle impostazioni di configurazione dell&#39;estensione:

1. Accedi a [experience.adobe.com](https://experience.adobe.com)
1. Seleziona **[!UICONTROL Data Collection]** nel menu di accesso rapido o il selettore di prodotto in alto a destra.
1. Selezionare **[!UICONTROL Tags]** nel menu di navigazione a sinistra.
1. Seleziona il tag desiderato da modificare.
1. Selezionare **[!UICONTROL Extensions]** nel menu di navigazione a sinistra.
1. Selezionare **[!UICONTROL Adobe Analytics]** nell&#39;elenco delle estensioni installate, quindi selezionare **[!UICONTROL Configure]** a destra.
1. Verificare che la casella di controllo **[!UICONTROL Use Activity Map]** sia abilitata.
1. Seleziona **[!UICONTROL Save]**.
1. Se necessario, crea le modifiche in una libreria e pubblicale in produzione.

Per ulteriori informazioni, consulta la [panoramica dell&#39;estensione Adobe Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/analytics/overview).

+++

+++Libreria JavaScript di Adobe Analytics (`AppMeasurement.js`)

Il modulo Activity Map gestisce la raccolta dati di Activity Map ed è incluso in tutte le librerie AppMeasurement v1.6 o versioni successive. È possibile esaminare il file `AppMeasurement.js` per assicurarsi che sia incluso.

1. Passa alla [versione più recente di Adobe Analytics AppMeasurement](https://github.com/adobe/appmeasurement/releases/latest) su GitHub.
1. Scarica il file della libreria AppMeasurement compresso, quindi apri `AppMeasurement.js` contenuto all&#39;interno.
1. Il modulo Activity Map è incluso nella parte superiore di questo file. Assicurati che questo modulo sia incluso nella libreria AppMeasurement utilizzata dal tuo sito.

+++

## Dimensioni disponibili

Quando Activity Map è abilitato sia per la suite di rapporti che per l’implementazione, puoi iniziare a utilizzare le dimensioni seguenti in Analysis Workspace:

* [[!UICONTROL Activity Map Link]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map Region]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Map Page]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Activity Map Link By Region]](/help/components/dimensions/activity-map-link-by-region.md)

## Scaricare e installare l’estensione del browser o il componente aggiuntivo

Oltre alle dimensioni disponibili in Analysis Workspace, puoi anche visualizzare i dati di Activity Map come sovrapposizione sul sito web. Per visualizzare questa sovrapposizione, scarica e installa l’estensione del browser Activity Map o il componente aggiuntivo.

**[!UICONTROL Tools]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Download Activity Map]**

Questo collegamento ti porta all’estensione o al marketplace dei componenti aggiuntivi supportati dal browser in cui puoi installarlo. Una volta installato, l’estensione o il componente aggiuntivo viene visualizzato in alto a destra del browser, dove puoi accedere e abilitare la sovrapposizione.
