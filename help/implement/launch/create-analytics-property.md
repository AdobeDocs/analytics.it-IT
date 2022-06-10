---
title: Creare una proprietà Analytics nei tag
description: Crea uno spazio per personalizzare la modalità di raccolta dei dati utilizzando i tag .
feature: Launch Implementation
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 5%

---

# Creare una proprietà tag in Adobe Analytics

I tag in Adobe Experience Platform consentono di integrare soluzioni Experience Cloud sul sito web (incluso Analytics). Questa pagina illustra in particolare come un amministratore di tag può configurare correttamente un’implementazione di base di Adobe Analytics.

## Prerequisiti 

[Creare una suite di rapporti](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Crea un silos per i dati di Analytics da raccogliere.

## Creare una proprietà tag e installare estensioni vitali

Le proprietà sono contenitori principali utilizzati per gestire i tag. Le estensioni ti consentono di installare tag specifici per il prodotto e configurarli.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic su **[!UICONTROL New Property]**.
1. Assegna alla proprietà un nome, ad esempio il titolo del sito web, e immetti il dominio su cui intendi implementare Analytics. Fai clic su **[!UICONTROL Save]**.
1. Fai clic sulla nuova proprietà tag creata per inserirne le impostazioni.
1. Fai clic sul pulsante **[!UICONTROL Extensions]** scheda , quindi fai clic su **[!UICONTROL Catalog]**.
1. Individua &quot;Servizio ID Experience Cloud&quot;, quindi fai clic su **[!UICONTROL Install]**.
1. Tutte le impostazioni, incluso l’ID organizzazione Experience Cloud, devono essere già compilate. Fai clic su **[!UICONTROL Save]**.
1. Nel catalogo delle estensioni, individua Adobe Analytics e fai clic su **[!UICONTROL Install]**.

Vedi la documentazione completa per [Estensione Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=it) per informazioni più dettagliate.

## Creazione di elementi dati per Adobe Analytics

Gli elementi dati sono riferimenti a parti specifiche del sito per raccogliere valori variabili.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fai clic sul pulsante **[!UICONTROL Data Elements]** scheda , quindi fai clic su **[!UICONTROL Add Data Element]**.
1. Assegna all’elemento dati le seguenti impostazioni:

   * Nome: Nome pagina
   * Estensione: Core
   * Tipo di elemento dati: Variabile JavaScript
   * Nome della variabile JavaScript: `window.document.title`

      >[!NOTE]
      >
      >Questo valore funge da esempio per iniziare. Se la tua organizzazione definisce un valore migliore per il nome della pagina, ad esempio un valore del livello dati, puoi immetterlo qui.
   * Testo pulito selezionato
   * Durata di conservazione: Nessuno
1. Fai clic su **[!UICONTROL Save]**.

## Creare regole per Adobe Analytics

Le regole mappano gli elementi dati ai valori delle variabili di Analytics e determinano quando tali valori vengono inviati ai server di Adobe.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fai clic sul pulsante **[!UICONTROL Rules]** scheda , quindi fai clic su **[!UICONTROL Add Rule]**. Denomina `Global Rule`.
1. Fai clic su **[!UICONTROL Add]** accanto agli eventi e immettere le impostazioni seguenti:
   * Estensione: Core
   * Tipo evento: Libreria caricata (Pagina in alto)
   * Nome: Core - Libreria caricata (pagina in alto)
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. Sotto **[!UICONTROL Actions]**, fai clic su **[!UICONTROL Add]** e immetti le seguenti impostazioni:
   * Estensione: Adobe Analytics
   * Tipo azione: Imposta variabili
   * Nome pagina: fai clic sull’icona del contenitore e seleziona la `Page Name` elemento dati.
   * Campagna: Parametro query con valore di `cid`
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. Fai clic sul segno più accanto alle azioni per aggiungere un’altra azione e immetti le seguenti impostazioni:
   * Estensione: Adobe Analytics
   * Tipo azione: Invia beacon
   * Nome: Adobe Analytics - Invia beacon
   * Tracciamento: s.t()
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. Verifica di aver impostato l&#39;evento e due azioni, quindi fai clic su **[!UICONTROL Save]**.

## Passaggi successivi

[Implementazione di Analytics nell’ambiente di sviluppo](deploy-dev.md): Ottieni il codice Analytics che funziona in un ambiente di test.
