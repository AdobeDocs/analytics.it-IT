---
title: Creare una proprietà Analytics in Launch
description: Create uno spazio per personalizzare il modo in cui vengono raccolti i dati, utilizzando  Adobe Experience Platform Launch.
translation-type: tm+mt
source-git-commit: dd506bf171c480c880863c03eee55be8fd9e15cb
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 4%

---


# Creare una proprietà Analytics in  Adobe Experience Platform Launch

 Adobe Experience Platform Launch è lo strumento che puoi utilizzare per integrare soluzioni  Experience Cloud sul tuo sito Web (inclusa Analytics). In questa pagina viene illustrato in che modo un amministratore di Launch può configurare correttamente un&#39;implementazione di base  Adobe Analytics.

## Prerequisiti

[Crea una suite](/help/admin/admin-console/create-report-suite.md)di rapporti: Creare un silo per i dati di Analytics da raccogliere

## Creare una proprietà e installare estensioni vitali

Le proprietà sono contenitori sovrapposti che consentono di gestire i tag. Le estensioni consentono di installare tag specifici del prodotto e configurarli.

1. Andate a [launch.adobe.com](https://launch.adobe.com) ed effettuate l&#39;accesso, se richiesto.
1. Fai clic su **[!UICONTROL New Property]**.
1. Assegna alla tua proprietà un nome, ad esempio il titolo del tuo sito Web, e immetti il dominio sul quale vuoi implementare Analytics. Fai clic su **[!UICONTROL Save]**.
1. Fate clic sulla nuova proprietà creata per specificarne le impostazioni.
1. Click the **[!UICONTROL Extensions]** tab, then click **[!UICONTROL Catalog]**.
1. Individua servizio identità, quindi fai clic su **[!UICONTROL Install]**.
1. Tutte le impostazioni, incluso  ID organizzazione Experience Cloud, devono essere già compilate. Fai clic su **[!UICONTROL Save]**.
1. Nel catalogo delle estensioni, individuare  Adobe Analytics e fare clic su **[!UICONTROL Install]**.

## Creazione di elementi dati per  Adobe Analytics

Gli elementi dati sono riferimenti a parti specifiche del sito per la raccolta di valori variabili.

1. Andate a [launch.adobe.com](https://launch.adobe.com) ed effettuate l&#39;accesso, se richiesto.
1. Fare clic sulla proprietà Launch che si desidera implementare sul sito.
1. Click the **[!UICONTROL Data Elements]** tab, then click **[!UICONTROL Create New Data Element]**.
1. Assegna all’elemento dati le seguenti impostazioni:

   * Nome: Nome pagina
   * Estensione: Core
   * Tipo elemento dati: Variabile JavaScript
   * Percorso della variabile: `window.document.title`

      >[!NOTE]
      >
      >Si tratta di un valore di esempio per iniziare a utilizzarlo. Se l’organizzazione definisce un valore migliore per il nome della pagina, ad esempio un valore per il livello dati, potete immetterlo qui.
   * Testo pulito selezionato
   * Durata: Pageview
1. Fai clic su **[!UICONTROL Save]**.

## Creare regole per  Adobe Analytics

Le regole associano gli elementi dati ai valori delle variabili Analytics e determinano quando tali valori vengono inviati  server  Adobi.

1. Andate a [launch.adobe.com](https://launch.adobe.com) ed effettuate l&#39;accesso, se richiesto.
1. Fare clic sulla proprietà Launch che si desidera implementare sul sito.
1. Fate clic **[!UICONTROL Create New Rule]** e denominatelo `Global Rule`.
1. Fate clic su **[!UICONTROL Add]** accanto agli eventi e immettete le seguenti impostazioni:
   * Estensione: Core
   * Tipo evento: Libreria Caricata (pagina in alto)
   * Nome: Core - Libreria caricata (Page Top)
   * Ordine: 50
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. In **[!UICONTROL Actions]**, fate clic **[!UICONTROL Add]** e immettete le seguenti impostazioni:
   * Estensione:  Adobe Analytics
   * Tipo azione: Imposta variabili
   * Nome pagina: fate clic sull&#39;icona del contenitore e selezionate l&#39;elemento `Page Name` dati.
   * Campaign: Parametro query con valore di `cid`
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. Fai clic sul segno più accanto alle azioni per aggiungere un’altra azione e immetti le seguenti impostazioni:
   * Estensione:  Adobe Analytics
   * Tipo azione: Invia beacon
   * Nome:  Adobe Analytics - Send Beacon
   * Tracciamento: s.t()
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. Verificate di avere impostato l&#39;evento e due azioni, quindi fate clic su **[!UICONTROL Save]**.

## Documentazione e risorse aggiuntive

* [documentazione](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension)sulle estensioni Adobe Analytics: Documentazione completa specifica per l’estensione  Adobe Analytics in  Adobe Experience Platform Launch.
* [Guida introduttiva a Launch](https://docs.adobelaunch.com/getting-started): Documentazione completa su Launch, inclusa una guida introduttiva più dettagliata
* [Canale](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&amp;shelf_id=0&amp;sort=dd)Adobe Experience Platform Launch YouTube: Scopri come utilizzare Launch tramite i video

## Passaggi successivi

[Distribuisci l’implementazione di Analytics nel tuo ambiente](deploy-dev.md)di sviluppo: Ottenete il codice Analytics in un ambiente di test.
