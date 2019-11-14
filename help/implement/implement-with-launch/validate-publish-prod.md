---
title: Implementare Adobe Analytics in un ambiente di sviluppo
description: Scopri come utilizzare Adobe Experience Platform Launch per distribuire Adobe Analytics al tuo ambiente di sviluppo.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Convalidare un'implementazione di sviluppo e pubblicare in produzione

Una volta avviata la produzione della libreria Adobe Experience Platform Launch, l'azienda può iniziare a utilizzare Adobe Analytics per creare report di base.

## Prerequisiti

[Distribuisci l’implementazione di Analytics nel tuo ambiente](deploy-dev.md)di sviluppo: Per seguire questa pagina, è necessario pubblicare un'implementazione di Analytics nel proprio ambiente di sviluppo.

## Convalida dell’implementazione di sviluppo tramite Experience Cloud Debugger

Experience Cloud Debugger è un plug-in Chrome che mostra tutti i tag Experience Cloud presenti in una pagina.

1. Apri [Chrome Web Browser](https://www.google.com/chrome/) e vai ad [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) su Chrome Web Store per installare l'estensione.
2. Andate al sito Web di sviluppo in cui avete implementato Launch.
3. Fai clic sull’icona Adobe Experience Cloud Debugger in alto a destra in Chrome
4. Se tutto è correttamente implementato, dovresti vedere il contenuto in Adobe Analytics, Adobe Experience Platform Launch e il servizio ID visitatori di Adobe Experience Cloud:

![debugger][assets/debugger.png]

## Implementare l'implementazione di dev per l'staging/prod

Dopo aver convalidato la visualizzazione dei dati, puoi inviare l'implementazione alla versione dal vivo del sito.

1. Vai ad [Adobe Experience Platform Launch](https://launch.adobe.com) ed effettua l'accesso, se richiesto.
2. Fare clic sulla proprietà Launch che si desidera implementare sul sito.
3. Fate clic sulla scheda Pubblicazione e individuate la libreria nella colonna di sviluppo.
4. Fate clic sul menu a discesa della libreria, quindi selezionate Invia per approvazione. Fare clic su Invia nella finestra modale.
5. Fate di nuovo clic sul menu a discesa della libreria (ora nella colonna Inviato), quindi selezionate Genera per gestione temporanea.
6. Dopo alcuni istanti, la luce gialla colorata della libreria diventa verde, a indicare che la creazione è stata completata correttamente.
7. Fate nuovamente clic sul menu a discesa della libreria e selezionate Approva per la pubblicazione.
8. Fate di nuovo clic sul menu a discesa della libreria (ora nella colonna Approvato), quindi selezionate Genera e Pubblica nella produzione.
9. Passate alla scheda Ambienti e fate clic su Ambiente di produzione.
10. Copiate l’intestazione di produzione + il codice piè di pagina e inviatelo ai proprietari del sito Web. Richiedi che implementino questo codice nell'ambiente di produzione del tuo sito.

## Convalida dell’implementazione di produzione

Conferma di visualizzare i dati sulla versione dal vivo del tuo sito e inizia la raccolta dati ufficiale per Adobe Analytics.

1. Una volta confermato dai proprietari del sito Web che hanno inviato il codice Launch alla produzione, passa alla home page del sito Web in Chrome e apri Adobe Experience Cloud Debugger.
2. Se tutto funziona, dovresti vedere dati simili ai tuoi test nell'ambiente di sviluppo. A questo punto, state raccogliendo dati sul vostro sito e ora potete iniziare a utilizzare Adobe Analytics per il reporting.

## Risoluzione dei problemi

**Nessun dato viene visualizzato nel debugger.**

Sul sito, aprite la console per sviluppatori del browser (in genere F12). Osservate il codice sorgente della pagina e accertatevi che siano soddisfatte le seguenti condizioni:

* Nella console non sono presenti errori JavaScript. Collabora con i proprietari del sito Web della tua organizzazione per verificare che tutti gli errori JS siano risolti.
* Il codice intestazione è implementato correttamente: Verificate che il codice dell'intestazione sia all'interno del `<head>` tag e che il file esista.
* Libreria AppMeasurement esistente: Andate direttamente all'origine JS per essere sicuri che il file JS contenga del codice. In caso contrario, accertatevi che ogni ambiente sia creato e che la libreria sia pubblicata nel rispettivo ambiente.
* Plug-in di interesse: Alcuni plug-in Chrome possono impedire l'attivazione di richieste di immagini. Disattiva eventuali plug-in che potrebbero impedire l'invio di dati ai server Adobe.

## Passaggi successivi

Ora che è stata configurata un'implementazione di base, il vostro ruolo all'interno dell'organizzazione può influenzare il percorso sul quale desiderate ulteriori informazioni:

* [Crea un documento](../prepare/solution-design.md)di progettazione della soluzione: Pianificare l'utilizzo di variabili personalizzate, quindi includerle nell'implementazione
* [Guida introduttiva ad Analysis Workspace](/help/analyze/analysis-workspace/home.md): Approfondisci Adobe Analytics con la funzionalità di punta dello strumento.
