---
title: Implementare Adobe Analytics in un ambiente di sviluppo
seo-title: Implementare Adobe Analytics in un ambiente di sviluppo
description: Scopri come utilizzare Adobe Experience Platform Launch per distribuire Adobe Analytics nell'ambiente di sviluppo.
seo-description: Scopri come utilizzare Adobe Experience Platform Launch per distribuire Adobe Analytics nell'ambiente di sviluppo.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Convalidare un'implementazione di sviluppo e pubblicare in produzione

Una volta avviata la libreria Adobe Experience Platform Launch, la tua organizzazione può iniziare a utilizzare Adobe Analytics per estrarre i rapporti di base.

## Prerequisiti

[Distribuisci l'implementazione di Analytics nell'ambiente di sviluppo](deploy-dev.md): Per seguire questa pagina, è necessario pubblicare un'implementazione Analytics nell'ambiente di sviluppo.

## Convalida della tua implementazione con il debugger Experience Cloud

Il debugger Experience Cloud è un plug-plugin Chrome che mostra tutti i tag Experience Cloud presenti in una pagina.

1. Open [Chrome Web Browser](https://www.google.com/chrome/) and go to [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) on the Chrome Web Store to install the extension.
2. Passate al sito Web in cui avete implementato Launch.
3. Fate clic sull'icona di debugger di Adobe Experience Cloud in alto a destra di Chrome
4. Se tutto è stato implementato correttamente, dovresti visualizzare il contenuto in Adobe Analytics, Adobe Experience Platform Launch e il servizio ID visitatori di Adobe Experience Cloud:

![debugger][assets/debugger.png]

## Implementare l'implementazione di tutti gli sviluppatori in pre-produzione/prod

Dopo aver convalidato i dati, potete inviare la vostra implementazione alla versione live del sito.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Fate clic sulla proprietà Launch che intendete implementare sul sito.
3. Fate clic sulla scheda Pubblicazione e individuate la libreria nella colonna di sviluppo.
4. Fate clic sul menu a discesa nella libreria, quindi selezionate Invia per approvazione. Fate clic su Invia nella finestra modale.
5. Fai di nuovo clic sul menu a discesa della libreria (ora nella colonna Inviato), quindi seleziona Genera per Staging.
6. Dopo alcuni istanti, la luce colorata giallo sulla libreria diventa verde e indica una build positiva.
7. Fate di nuovo clic sul menu a discesa della libreria e selezionate Approva per pubblicazione.
8. Fate di nuovo clic sul menu a discesa della libreria (ora nella colonna Approvato), quindi selezionate Genera e pubblica su produzione.
9. Passate alla scheda Ambienti, fate clic su Ambiente di produzione.
10. Copiate il codice di intestazione + piè di pagina e distribuitelo ai proprietari del sito Web. Richiedete di implementare questo codice nell'ambiente di produzione del sito.

## Convalida dell'implementazione di produzione

Conferma di visualizzare i dati sulla versione dal vivo del sito e di iniziare la raccolta dati ufficiale per Adobe Analytics.

1. Dopo aver confermato ai proprietari del sito Web che hanno inviato il codice di avvio alla produzione, passa alla pagina iniziale del sito Web in Chrome e apri il debugger di Adobe Experience Cloud.
2. Se tutto funziona, dovresti visualizzare dati simili ai test nell'ambiente di sviluppo. A questo punto, state raccogliendo dati sul sito e ora potete iniziare a utilizzare Adobe Analytics per la generazione di rapporti.

## Risoluzione dei problemi   

**Nel debugger non vengono visualizzati dati.**

Nel sito, aprite la console per sviluppatori del browser (in genere F 12). Osservate il codice sorgente della pagina e verificate che siano soddisfatte le seguenti condizioni:

* Nella console non sono presenti errori javascript. Per verificare che tutti gli errori JS siano risolti, rivolgetevi ai proprietari del sito Web della vostra organizzazione.
* Header code is properly implemented: Make sure the header code is inside the `<head>` tag, and that the file exists.
* Libreria appmeasurement: Andate direttamente all'origine JS per assicurarvi che il file JS contenga del codice. In caso contrario, assicuratevi che sia creato ciascun ambiente e che la libreria venga pubblicata nel rispettivo ambiente.
* Plug-in interferiti: Alcuni plug-in Chrome possono impedire l'attivazione di richieste di immagini. Disattiva i plug-in che potrebbero interrompere l'invio dei dati ai server Adobe.

## Passaggi successivi

Ora che è stata configurata un'implementazione di base, il tuo ruolo all'interno dell'organizzazione può influenzare il percorso sul quale vuoi saperne di più:

* [Creare un documento di progettazione della soluzione](../prepare/solution-design.md): Come pianificare la modalità di utilizzo delle variabili personalizzate e includerle nell'implementazione
* [Guida introduttiva ad Analysis Workspace](../../analyze/analysis-workspace/home.md): Immergiti direttamente in Adobe Analytics utilizzando la funzionalità di punta dello strumento.
