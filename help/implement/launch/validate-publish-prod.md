---
title: Convalidare un'implementazione di sviluppo e pubblicare in produzione
description: Scoprite come utilizzare  Adobe Experience Platform Launch per distribuire  Adobe Analytics nell'ambiente di produzione.
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 4%

---


# Convalidare un&#39;implementazione di sviluppo e pubblicare in produzione

Una volta avviata la produzione della libreria Adobe Experience Platform Launch , l&#39;azienda può iniziare a utilizzare  Adobe Analytics per creare rapporti di base.

## Prerequisiti

[Distribuisci l’implementazione di Analytics nel tuo ambiente](deploy-dev.md)di sviluppo: Per seguire questa pagina, è necessario pubblicare un&#39;implementazione di Analytics nel proprio ambiente di sviluppo.

## Convalidare l’implementazione di dev utilizzando il debugger del Experience Cloud 

Il debugger  Experience Cloud è un plug-in Chrome che mostra tutti  tag Experience Cloud presenti in una pagina.

1. Aprite [Chrome Web Browser](https://www.google.com/chrome/) e andate a [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) su Chrome Web Store per installare l&#39;estensione.
2. Andate al sito Web di sviluppo in cui avete implementato Launch.
3. Fare clic sull&#39;icona Adobe Experience Cloud Debugger in alto a destra di Chrome
4. Se tutto è correttamente implementato, dovresti vedere il contenuto  Adobe Analytics,  Adobe Experience Platform Launch e il servizio ID visitatori di Adobe Experience Cloud:

![debugger][assets/debugger.png]

## Implementare l&#39;implementazione di dev per la messa in scena/prod

Dopo aver convalidato la visualizzazione dei dati, puoi inviare l&#39;implementazione alla versione dal vivo del sito.

1. Accedete a [Adobe Experience Platform Launch](https://launch.adobe.com) e, se richiesto, effettuate l’accesso.
2. Fare clic sulla proprietà Launch che si desidera implementare sul sito.
3. Fate clic sulla scheda Pubblicazione e individuate la libreria nella colonna di sviluppo.
4. Fate clic sul menu a discesa della libreria, quindi selezionate Invia per approvazione. Fare clic su Invia nella finestra modale.
5. Fate di nuovo clic sul menu a discesa della libreria (ora nella colonna Inviato), quindi selezionate Genera per gestione temporanea.
6. Dopo alcuni istanti, la luce gialla colorata della libreria diventa verde, a indicare che la creazione è stata completata correttamente.
7. Fate nuovamente clic sul menu a discesa della libreria e selezionate Approva per la pubblicazione.
8. Fate di nuovo clic sul menu a discesa della libreria (ora nella colonna Approvato), quindi selezionate Genera e Pubblica nella produzione.
9. Passate alla scheda Ambienti e fate clic su Ambiente di produzione.
10. Copiate l’intestazione di produzione + il codice piè di pagina e inviatelo ai proprietari del sito Web. Richiedi che implementino questo codice nell&#39;ambiente di produzione del tuo sito.

## Convalida dell’implementazione di produzione

Conferma di visualizzare i dati sulla versione dal vivo del tuo sito e inizia la raccolta dati ufficiale per  Adobe Analytics.

1. Una volta confermato dai proprietari del sito Web che hanno inviato il codice Launch alla produzione, andate alla home page del sito Web in Chrome e aprite il debugger Adobe Experience Cloud.
2. Se tutto funziona, dovresti vedere dati simili ai tuoi test nell&#39;ambiente di sviluppo. A questo punto, state raccogliendo dati sul sito e ora potete iniziare a utilizzare  Adobe Analytics per il reporting.

## Risoluzione dei problemi

**Nessun dato viene visualizzato nel debugger.**

Sul sito, aprite la console per sviluppatori del browser (in genere F12). Osservate il codice sorgente della pagina e accertatevi che siano soddisfatte le seguenti condizioni:

* Nella console non sono presenti errori JavaScript. Collabora con i proprietari del sito Web della tua organizzazione per essere certi che tutti gli errori JS vengano risolti.
* Il codice intestazione è implementato correttamente: Verificate che il codice dell&#39;intestazione sia all&#39;interno del `<head>` tag e che il file esista.
* Libreria AppMeasurement esistente: Andate direttamente all&#39;origine JS per essere sicuri che il file JS contenga del codice. In caso contrario, accertatevi che ogni ambiente sia creato e che la libreria sia pubblicata nel relativo ambiente.
* Plug-in di interesse: Alcuni plug-in Chrome possono impedire l’attivazione di richieste di immagini. Disattiva i plug-in che potrebbero impedire l&#39;invio dei dati  server  Adobi.

## Passaggi successivi

Ora che è impostata un&#39;implementazione di base, il vostro ruolo all&#39;interno dell&#39;organizzazione può influenzare il percorso sul quale desiderate ulteriori informazioni:

* [Crea un documento](../prepare/solution-design.md)di progettazione della soluzione: Pianificare l&#39;utilizzo di variabili personalizzate, quindi includerle nell&#39;implementazione
* [Inizia a usare  Analysis Workspace](/help/analyze/analysis-workspace/home.md):  Adobe Analytics con la funzionalità di punta dello strumento.
