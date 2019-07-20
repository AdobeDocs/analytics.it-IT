---
title: Creare una proprietà Analytics in Launch
seo-title: Creare una proprietà Adobe Analytics in Adobe Experience Platform Launch
description: Crea uno spazio per personalizzare il modo in cui vengono raccolti i dati, utilizzando Adobe Experience Platform Launch.
seo-description: Crea uno spazio per personalizzare il modo in cui i dati vengono raccolti in Adobe Analytics utilizzando Adobe Experience Platform Launch.
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Creare una proprietà Analytics in Adobe Experience Platform Launch

Adobe Experience Platform Launch è lo strumento che puoi usare per integrare soluzioni Experience Cloud sul tuo sito Web (inclusa Analytics). Questa pagina indica in maniera specifica come un amministratore di Launch può ottenere un'implementazione di base di Adobe Analytics configurata correttamente.

## Prerequisiti

[Crea una suite di rapporti](../../admin/admin-console/create-report-suite.md): Creare un silo per i dati di Analytics da raccogliere

## Creazione di una proprietà e installazione di estensioni fondamentali

Le proprietà sono i contenitori che utilizzate per gestire i tag. Le estensioni consentono di installare tag specifici per il prodotto e di configurarli.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. Fate clic su Nuova proprietà.
1. Assegna alla proprietà un nome, ad esempio il titolo del sito Web, e immetti il dominio sul quale intendi implementare Analytics. Fate clic su Salva.
1. Fate clic sulla nuova proprietà appena creata per inserirne le impostazioni.
1. Fare clic sulla scheda Estensioni, quindi su Catalogo.
1. Individua Servizio identità, quindi fai clic su Installa.
1. Tutte le impostazioni, incluso l'ID organizzazione Experience Cloud, devono essere già compilate. Fate clic su Salva.
1. Nel catalogo delle estensioni, individuate Adobe Analytics e fate clic su Installa.

## Creazione di elementi di dati per Adobe Analytics

Gli elementi dati sono riferimenti a parti specifiche del sito per raccogliere valori variabili.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
2. Fate clic sulla proprietà Launch che intendete implementare sul sito.
3. Fai clic sulla scheda Elementi dati, quindi fai clic su Crea nuovo elemento dati.
4. Assegna all'elemento dati le seguenti impostazioni:
   * Nome: Nome pagina
   * Estensione: Core
   * Tipo elemento dati: Variabile javascript
   * Path to variable: `window.document.title`
      > [!NOTE] Nota: Questo è un valore di esempio per iniziare a utilizzare. Se la vostra organizzazione definisce un valore migliore per il nome della pagina, ad esempio un valore di livello dati, potete inserirlo qui.
   * Testo pulito selezionato
   * Durata: Visualizzazione pagina
5. Fate clic su Salva.

## Creare regole per Adobe Analytics

Le regole mappano gli elementi dati sui valori delle variabili di Analytics e determinano quando tali valori vengono inviati ai server di Adobe.

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. Fate clic sulla proprietà Launch che intendete implementare sul sito.
1. Click Create New Rule and name it `Global Rule`.
1. Fate clic su Aggiungi accanto agli eventi e immettete le seguenti impostazioni:
   * Estensione: Core
   * Tipo evento: Libreria caricata (Pagina in alto)
   * Nome: Core - Libreria caricata (Pagina in alto)
   * Ordine: 50
1. Fate clic su Mantieni modifiche.
1. In Azioni, fate clic su Aggiungi e immettete le seguenti impostazioni:
   * Estensione: Adobe Analytics
   * Tipo di azione: Imposta variabili
   * Page Name: click the container icon, and select the `Page Name` data element.
   * Campaign: Query parameter with a value of `cid`
1. Fate clic su Mantieni modifiche.
1. Fai clic sul segno più accanto alle azioni per aggiungere un'altra azione, quindi immetti le seguenti impostazioni:
   * Estensione: Adobe Analytics
   * Tipo di azione: Invia beacon
   * Nome: Adobe Analytics - Send Beacon
   * Tracciamento: s. t ()
1. Fate clic su Mantieni modifiche.
1. Verificate di disporre dell'evento e di due azioni, quindi fate clic su Salva.

## Documentazione e risorse aggiuntive

* [Documentazione dell'estensione Adobe Analytics](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension): Documentazione completa relativa all'estensione Adobe Analytics in Adobe Experience Platform Launch.
* [Guida introduttiva all'avvio](https://docs.adobelaunch.com/getting-started): Documentazione completa per Launch, inclusa una guida introduttiva più dettagliata
* [Canale YouTube di Adobe Experience Platform](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd): Scopri come utilizzare Launch nei video

## Passaggi successivi

[Distribuisci l'implementazione di Analytics nell'ambiente di sviluppo](deploy-dev.md): Ottenere il codice Analytics in un ambiente di test.
