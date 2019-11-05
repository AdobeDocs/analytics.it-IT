---
title: Creare una proprietà Analytics in Launch
seo-title: Creare una proprietà Adobe Analytics in Adobe Experience Platform Launch
description: Crea uno spazio per personalizzare il modo in cui vengono raccolti i dati, utilizzando Adobe Experience Platform Launch.
seo-description: Crea uno spazio per personalizzare il modo in cui i dati vengono raccolti in Adobe Analytics, utilizzando Adobe Experience Platform Launch.
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Creazione di una proprietà Analytics in Adobe Experience Platform Launch

Adobe Experience Platform Launch è lo strumento che puoi usare per integrare le soluzioni Experience Cloud nel tuo sito Web (incluso Analytics). In questa pagina viene illustrato in che modo un amministratore di Launch può configurare correttamente un'implementazione di base di Adobe Analytics.

## Prerequisiti

[Crea una suite](/help/admin/admin-console/create-report-suite.md)di rapporti: Creare un silo per i dati di Analytics da raccogliere

## Creare una proprietà e installare estensioni vitali

Le proprietà sono contenitori sovrapposti che consentono di gestire i tag. Le estensioni consentono di installare tag specifici del prodotto e configurarli.

1. Andate a [launch.adobe.com](https://launch.adobe.com) ed effettuate l'accesso, se richiesto.
1. Fate clic su "Nuova proprietà".
1. Assegna alla proprietà un nome, ad esempio il titolo del tuo sito Web, e immetti il dominio sul quale vuoi implementare Analytics. Fate clic su Salva.
1. Fate clic sulla nuova proprietà creata per specificarne le impostazioni.
1. Fare clic sulla scheda Estensioni, quindi su Catalogo.
1. Individua servizio identità, quindi fai clic su Installa.
1. Tutte le impostazioni, incluso l’ID organizzazione Experience Cloud, devono essere già compilate. Fate clic su Salva.
1. Nel catalogo delle estensioni, individua Adobe Analytics e fai clic su Installa.

## Creazione di elementi dati per Adobe Analytics

Gli elementi dati sono riferimenti a parti specifiche del sito per raccogliere i valori variabili.

1. Andate a [launch.adobe.com](https://launch.adobe.com) ed effettuate l'accesso, se richiesto.
2. Fare clic sulla proprietà Launch che si desidera implementare sul sito.
3. Fare clic sulla scheda Elementi dati, quindi su Crea nuovo elemento dati.
4. Assegna all’elemento dati le seguenti impostazioni:
   * Nome: Nome pagina
   * Estensione: Core
   * Tipo elemento dati: Variabile JavaScript
   * Percorso della variabile: `window.document.title`
      > [!NOTE] Nota: Si tratta di un valore di esempio per iniziare a utilizzarlo. Se l’organizzazione definisce un valore migliore per il nome della pagina, ad esempio un valore per il livello dati, potete immetterlo qui.
   * Testo pulito selezionato
   * Durata:Pageview
5. Fate clic su Salva.

## Creare regole per Adobe Analytics

Le regole mappano gli elementi dati ai valori variabili di Analytics e determinano quando tali valori vengono inviati ai server Adobe.

1. Andate a [launch.adobe.com](https://launch.adobe.com) ed effettuate l'accesso, se richiesto.
1. Fare clic sulla proprietà Launch che si desidera implementare sul sito.
1. Fate clic su Crea nuova regola e denominatela `Global Rule`.
1. Fate clic su Aggiungi accanto agli eventi e immettete le seguenti impostazioni:
   * Estensione: Core
   * Tipo evento: Libreria Caricata (pagina in alto)
   * Nome: Core - Libreria caricata (Page Top)
   * Ordine: 50
1. Fare clic su Mantieni modifiche.
1. In Azioni, fai clic su Aggiungi e immetti le seguenti impostazioni:
   * Estensione:Adobe Analytics
   * Tipo azione: Imposta variabili
   * Nome pagina: fate clic sull'icona del contenitore e selezionate l'elemento `Page Name` dati.
   * Campaign: Parametro query con valore di `cid`
1. Fare clic su Mantieni modifiche.
1. Fai clic sul segno più accanto alle azioni per aggiungere un’altra azione e immetti le seguenti impostazioni:
   * Estensione:Adobe Analytics
   * Tipo azione: Invia beacon
   * Nome: Adobe Analytics - Send Beacon
   * Tracciamento: s.t()
1. Fare clic su Mantieni modifiche.
1. Verificate di avere impostato l'evento e due azioni, quindi fate clic su Salva.

## Documentazione e risorse aggiuntive

* [Documentazione](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension)sulle estensioni di Adobe Analytics: Documentazione completa specifica per l’estensione Adobe Analytics in Adobe Experience Platform Launch.
* [Guida introduttiva a Launch](https://docs.adobelaunch.com/getting-started): Documentazione completa su Launch, inclusa una guida introduttiva più dettagliata
* [Canale](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd)YouTube di Adobe Experience Platform: Scopri come utilizzare Launch tramite i video

## Passaggi successivi

[Distribuisci l’implementazione di Analytics nel tuo ambiente](deploy-dev.md)di sviluppo: Ottenete il codice Analytics in un ambiente di test.
