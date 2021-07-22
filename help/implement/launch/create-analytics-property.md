---
title: Creare una proprietà Analytics nei tag
description: Crea uno spazio per personalizzare la modalità di raccolta dei dati utilizzando i tag .
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 5%

---

# Creare una proprietà tag di Analytics

I tag in Adobe Experience Platform consentono di integrare soluzioni Experience Cloud sul sito web (incluso Analytics). Questa pagina illustra in particolare come un amministratore di tag può configurare correttamente un’implementazione di base di Adobe Analytics.

>[!NOTE]
>Adobe Experience Platform Launch è stato riclassificato come una suite di tecnologie di raccolta dati nell’Experience Platform. Di conseguenza, sono state introdotte diverse modifiche terminologiche nella documentazione del prodotto. Consulta questo [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) come riferimento consolidato delle modifiche terminologiche.

## Prerequisiti

[Creare una suite](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) di rapporti: Crea un silos per i dati di Analytics da raccogliere.

## Creare una proprietà tag e installare estensioni vitali

Le proprietà sono contenitori principali utilizzati per gestire i tag. Le estensioni ti consentono di installare tag specifici per il prodotto e configurarli.

1. Vai a [experience.adobe.com](https://experience.adobe.com) e accedi quando richiesto.
1. Select **[!UICONTROL Launch / Data Collection]**.
1. Fare clic su **[!UICONTROL Go to Launch / Data Collection]**, quindi selezionare **[!UICONTROL Tags]**.
1. Fai clic su **[!UICONTROL New Property]**.
1. Assegna alla proprietà un nome, ad esempio il titolo del sito web, e immetti il dominio su cui intendi implementare Analytics. Fai clic su **[!UICONTROL Save]**.
1. Fai clic sulla nuova proprietà tag creata per inserirne le impostazioni.
1. Fai clic sulla scheda **[!UICONTROL Extensions]** , quindi fai clic su **[!UICONTROL Catalog]**.
1. Individua il servizio Identity, quindi fai clic su **[!UICONTROL Install]**.
1. Tutte le impostazioni, incluso l’ID organizzazione Experience Cloud, devono essere già compilate. Fai clic su **[!UICONTROL Save]**.
1. Nel catalogo delle estensioni, individua Adobe Analytics e fai clic su **[!UICONTROL Install]**.

## Creazione di elementi dati per Adobe Analytics

Gli elementi dati sono riferimenti a parti specifiche del sito per raccogliere valori variabili.

1. Vai a [experience.adobe.com](https://experience.adobe.com) e accedi quando richiesto.
1. Selezionare **[!UICONTROL Launch / Data Collection]**.
1. Fare clic su **[!UICONTROL Go to Launch / Data Collection]**, quindi selezionare **[!UICONTROL Tags]**.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
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

1. Vai a [experience.adobe.com](https://experience.adobe.com) e accedi quando richiesto.
1. Selezionare **[!UICONTROL Launch / Data Collection]**.
1. Fare clic su **[!UICONTROL Go to Launch / Data Collection]**, quindi selezionare **[!UICONTROL Tags]**.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
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

* [Documentazione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en) dell&#39;estensione Adobe Analytics: Documentazione completa specifica per l’estensione Adobe Analytics nei tag.
* [Guida introduttiva ai tag](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en): Documentazione completa sui tag, inclusa una guida introduttiva più dettagliata
* [Canale](https://experienceleague.adobe.com/?tag=Launch#recommended/solutions/experience-platform) Adobe Experience Platform Launch: Scopri come utilizzare i tag nei video

## Passaggi successivi

[Implementare l&#39;implementazione di Analytics nell&#39;ambiente](deploy-dev.md) di sviluppo: Ottieni il codice Analytics che funziona in un ambiente di test.
