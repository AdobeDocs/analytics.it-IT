---
title: Creare una proprietà Analytics nei tag
description: Crea uno spazio per personalizzare la modalità di raccolta dei dati, utilizzando i tag.
feature: Launch Implementation
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 14%

---

# Creare una proprietà tag in Adobe Analytics

I tag in Adobe Experience Platform consentono di integrare soluzioni Experience Cloud sul sito web (incluso Analytics). Questa pagina illustra in modo specifico come un amministratore di tag può ottenere un’implementazione di base di Adobe Analytics configurata correttamente.

## Prerequisiti

[Creare una suite di rapporti](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): crea un silo per i dati di Analytics da raccogliere.

## Creare una proprietà tag e installare estensioni vitali

Le proprietà sono contenitori generali utilizzati per gestire i tag. Le estensioni consentono di installare tag specifici per il prodotto e configurarli.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic su **[!UICONTROL New Property]** (Usa modello di attribuzione non predefinito).
1. Assegna alla proprietà un nome, ad esempio il titolo del sito web, e immetti il dominio in cui intendi implementare Analytics. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).
1. Fai clic sulla nuova proprietà tag creata per immetterne le impostazioni.
1. Fai clic su **[!UICONTROL Extensions]** , quindi fai clic su **[!UICONTROL Catalog]**.
1. Individua &quot;Experience Cloud ID Service&quot;, quindi fai clic su **[!UICONTROL Install]**.
1. Tutte le impostazioni, incluso l’ID organizzazione Experience Cloud, devono essere già compilate. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).
1. Torna nel catalogo delle estensioni, individua Adobe Analytics e fai clic su **[!UICONTROL Install]**.

Consulta la documentazione completa per [Estensione Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=it) per informazioni più dettagliate.

## Creare elementi dati per Adobe Analytics

Gli elementi dati sono riferimenti a parti specifiche del sito per raccogliere valori di variabili.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fai clic su **[!UICONTROL Data Elements]** , quindi fai clic su **[!UICONTROL Add Data Element]**.
1. Attribuisci all’elemento dati le seguenti impostazioni:

   * Nome: nome della pagina
   * Estensione: Core
   * Tipo di elemento dati: variabile JavaScript
   * Nome variabile JavaScript: `window.document.title`

      >[!NOTE]
      >
      >Questo valore funge da esempio per iniziare. Se la tua organizzazione definisce un valore migliore per il nome della pagina, ad esempio un valore del livello dati, puoi immetterlo qui.
   * Pulisci testo selezionato
   * Durata archiviazione: nessuna
1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

## Creare regole per Adobe Analytics

Le regole mappano gli elementi dati ai valori delle variabili di Analytics e determinano quando tali valori vengono inviati ai server di Adobe.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fai clic su **[!UICONTROL Rules]** , quindi fai clic su **[!UICONTROL Add Rule]**. Assegna un nome `Global Rule`.
1. Clic **[!UICONTROL Add]** accanto a eventi e immettere le impostazioni seguenti:
   * Estensione: Core
   * Tipo evento: libreria caricata (parte superiore della pagina)
   * Nome: Core - Library Loaded (Page Top)
1. Fai clic su **[!UICONTROL Keep Changes]** (Usa modello di attribuzione non predefinito).
1. Sotto **[!UICONTROL Actions]**, fai clic su **[!UICONTROL Add]** e immetti le seguenti impostazioni:
   * Estensione: Adobe Analytics
   * Tipo azione: Imposta variabili
   * Nome pagina: fai clic sull’icona del contenitore e seleziona la `Page Name` elemento dati.
   * Campaign: parametro di query con valore `cid`
1. Fai clic su **[!UICONTROL Keep Changes]** (Usa modello di attribuzione non predefinito).
1. Fai clic sul segno Più accanto alle azioni per aggiungere un’altra azione, quindi immetti le seguenti impostazioni:
   * Estensione: Adobe Analytics
   * Tipo azione: invia beacon
   * Nome: Adobe Analytics - Invia beacon
   * Tracciamento: s.t()
1. Fai clic su **[!UICONTROL Keep Changes]** (Usa modello di attribuzione non predefinito).
1. Verifica che siano impostati l’evento e due azioni, quindi fai clic su **[!UICONTROL Save]**.

## Passaggi successivi

[Implementare Analytics nell’ambiente di sviluppo](deploy-dev.md): ottieni il codice Analytics che funziona in un ambiente di test.
