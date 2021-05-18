---
title: Creare una proprietà Analytics in Launch
description: Crea uno spazio per personalizzare la modalità di raccolta dei dati utilizzando Adobe Experience Platform Launch.
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: c46feec3f08b78ca7882193ab86914db49617c1c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Creare una proprietà Analytics in Adobe Experience Platform Launch

Adobe Experience Platform Launch è lo strumento che puoi utilizzare per integrare le soluzioni Experience Cloud sul tuo sito web (incluso Analytics). Questa pagina illustra in modo specifico come un amministratore di Launch può configurare correttamente un’implementazione di base di Adobe Analytics.

## Prerequisiti

[Creare una suite](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) di rapporti: Creare un silos per i dati di Analytics da raccogliere

## Creare una proprietà e installare estensioni vitali

Le proprietà sono contenitori principali utilizzati per gestire i tag. Le estensioni ti consentono di installare tag specifici per il prodotto e configurarli.

1. Vai a [launch.adobe.com](https://launch.adobe.com) e, se richiesto, accedi.
1. Fai clic su **[!UICONTROL New Property]**.
1. Assegna alla proprietà un nome, ad esempio il titolo del sito web, e immetti il dominio su cui intendi implementare Analytics. Fai clic su **[!UICONTROL Save]**.
1. Fai clic sulla nuova proprietà creata per inserirne le impostazioni.
1. Fai clic sulla scheda **[!UICONTROL Extensions]** , quindi fai clic su **[!UICONTROL Catalog]**.
1. Individua il servizio Identity, quindi fai clic su **[!UICONTROL Install]**.
1. Tutte le impostazioni, incluso l’ID organizzazione Experience Cloud, devono essere già compilate. Fai clic su **[!UICONTROL Save]**.
1. Nel catalogo delle estensioni, individua Adobe Analytics e fai clic su **[!UICONTROL Install]**.

## Creazione di elementi dati per Adobe Analytics

Gli elementi dati sono riferimenti a parti specifiche del sito per raccogliere valori variabili.

1. Vai a [launch.adobe.com](https://launch.adobe.com) e, se richiesto, accedi.
1. Fai clic sulla proprietà Launch che intendi implementare sul tuo sito.
1. Fai clic sulla scheda **[!UICONTROL Data Elements]** , quindi fai clic su **[!UICONTROL Create New Data Element]**.
1. Assegna all’elemento dati le seguenti impostazioni:

   * Nome: Nome pagina
   * Estensione: Core
   * Tipo di elemento dati: Variabile JavaScript
   * Percorso della variabile: `window.document.title`

      >[!NOTE]
      >
      >Questo è un valore di esempio per iniziare. Se la tua organizzazione definisce un valore migliore per il nome della pagina, ad esempio un valore del livello dati, puoi immetterlo qui.
   * Testo pulito selezionato
   * Durata: Pageview
1. Fai clic su **[!UICONTROL Save]**.

## Creare regole per Adobe Analytics

Le regole mappano gli elementi dati ai valori delle variabili di Analytics e determinano quando tali valori vengono inviati ai server di Adobe.

1. Vai a [launch.adobe.com](https://launch.adobe.com) e, se richiesto, accedi.
1. Fai clic sulla proprietà Launch che intendi implementare sul tuo sito.
1. Fare clic su **[!UICONTROL Create New Rule]** e denominarlo `Global Rule`.
1. Fai clic su **[!UICONTROL Add]** accanto agli eventi e immetti le seguenti impostazioni:
   * Estensione: Core
   * Tipo evento: Libreria caricata (Pagina in alto)
   * Nome: Core - Libreria caricata (pagina in alto)
   * Ordine: 50
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. In **[!UICONTROL Actions]**, fai clic su **[!UICONTROL Add]** e immetti le seguenti impostazioni:
   * Estensione: Adobe Analytics
   * Tipo azione: Imposta variabili
   * Nome pagina: fai clic sull’icona del contenitore e seleziona l’elemento dati `Page Name` .
   * Campagna: Parametro query con valore `cid`
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. Fai clic sul segno più accanto alle azioni per aggiungere un’altra azione e immetti le seguenti impostazioni:
   * Estensione: Adobe Analytics
   * Tipo azione: Invia beacon
   * Nome: Adobe Analytics - Invia beacon
   * Tracciamento: s.t()
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. Verifica di aver impostato l&#39;evento e due azioni, quindi fai clic su **[!UICONTROL Save]**.

## Documentazione e risorse aggiuntive

* [Documentazione](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html?lang=en#extensions-ref) dell&#39;estensione Adobe Analytics: Documentazione completa specifica per l’estensione Adobe Analytics in Adobe Experience Platform Launch.
* [Guida introduttiva a Launch](https://experienceleague.adobe.com/docs/launch/using/get-started/quick-start.html?lang=en#get-started): Documentazione completa su Launch, inclusa una guida introduttiva più dettagliata
* [Canale](https://experienceleague.adobe.com/?tag=Launch#recommended/solutions/experience-platform) Adobe Experience Platform Launch: Scopri come utilizzare Launch tramite i video

## Passaggi successivi

[Implementare l&#39;implementazione di Analytics nell&#39;ambiente](deploy-dev.md) di sviluppo: Ottieni il codice Analytics che funziona in un ambiente di test.
