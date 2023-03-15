---
title: Convalidare un'implementazione di sviluppo e pubblicare in produzione
description: Scopri come utilizzare i tag Adobe Experience Platform per distribuire Adobe Analytics nell’ambiente di produzione.
feature: Launch Implementation
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 7%

---

# Convalidare un&#39;implementazione di sviluppo e pubblicare in produzione

Una volta che la libreria di tag è stata inviata in produzione, la tua organizzazione può iniziare a utilizzare Adobe Analytics per richiamare rapporti di base.

## Prerequisiti

[Implementare Analytics nell’ambiente di sviluppo](deploy-dev.md): per seguire questa pagina, è necessario pubblicare un’implementazione di Analytics nell’ambiente di sviluppo.

## Convalidare l’implementazione di sviluppo utilizzando Experience Cloud Debugger

Experience Cloud Debugger è un’estensione che mostra tutti i tag Experience Cloud presenti in una pagina.

1. Installare l’estensione per [Chrome](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) o [Firefox](https://addons.mozilla.org/it/firefox/addon/adobe-experience-platform-dbg/).
2. Vai al tuo sito web di sviluppo su cui hai implementato i tag.
3. Fai clic sull’icona di Adobe Experience Cloud Debugger nel browser.
4. Se tutto è implementato correttamente, dovresti visualizzare il contenuto all’interno di Adobe Analytics, i tag e il servizio ID visitatore di Adobe Experience Cloud.

## Implementare l’implementazione di sviluppo in staging/produzione

Una volta verificato che i dati sono visibili, puoi inviare l’implementazione alla versione live del sito.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fai clic su **[!UICONTROL Publishing]** e individuare la libreria nella colonna sviluppo.
1. Fai clic sul menu a discesa della libreria, quindi seleziona **[!UICONTROL Submit for Approval]**. Clic **[!UICONTROL Submit]** nella finestra modale.
1. Fai nuovamente clic sul menu a discesa della libreria (ora nella colonna Inviato), quindi seleziona **[!UICONTROL Build for Staging]**.
1. Dopo alcuni istanti, la luce gialla colorata sulla libreria diventa verde, a indicare una build di successo.
1. Fai nuovamente clic sul menu a discesa della libreria e seleziona **[!UICONTROL Approve for Publishing]**.
1. Fai di nuovo clic sul menu a discesa della libreria (ora nel [!UICONTROL Approved] ) e selezionare **[!UICONTROL Build and Publish to Production]**.
1. Vai alla scheda Ambienti e fai clic su **[!UICONTROL Production Environment]**.
1. Copia il codice di installazione di produzione e forniscilo ai proprietari del tuo sito web. Richiedi l&#39;implementazione di questo codice nell&#39;ambiente di produzione del tuo sito.

## Convalidare l’implementazione di produzione

Verifica di visualizzare i dati sulla versione live del sito e avvia la raccolta dati ufficiale per Adobe Analytics.

1. Dopo aver confermato dai proprietari del sito web di aver inviato il codice tag in produzione, accedi alla home page del sito web in Chrome e apri la [!UICONTROL Adobe Experience Cloud debugger].
2. Se tutto funziona, nell’ambiente di sviluppo dovrebbero essere visualizzati dati simili ai test. A questo punto, stai raccogliendo dati sul tuo sito e ora puoi iniziare a utilizzare Adobe Analytics per il reporting.

## Risoluzione dei problemi

**Nel debugger non viene visualizzato alcun dato.**

Sul sito, apri la console per sviluppatori del browser (in genere F12). Osserva il codice sorgente della pagina e accertati che siano soddisfatte le seguenti condizioni:

* Nessun errore JavaScript nella console. Rivolgiti ai proprietari del sito web della tua organizzazione per assicurarti che tutti gli errori JS siano stati risolti.
* Il codice intestazione è implementato correttamente: assicurati che il codice intestazione sia all’interno del `<head>` e che il file esista.
* Esiste già una libreria AppMeasurement: passa direttamente all’origine JS per assicurarti che il file JS contenga codice. In caso contrario, assicurati che ogni ambiente sia stato creato e che la libreria sia stata pubblicata nel rispettivo ambiente.
* Estensioni di interferenza: alcune estensioni, come ad blocker, possono impedire l’attivazione delle richieste di immagini. Disattiva le estensioni che potrebbero impedire l’invio dei dati ad Adobe.

## Passaggi successivi

Ora che è stata configurata un’implementazione di base, il tuo ruolo all’interno dell’organizzazione può influenzare il percorso su cui desideri saperne di più:

* [Creare un documento di progettazione della soluzione](../prepare/solution-design.md): crea un piano per l’utilizzo delle variabili personalizzate, quindi includile nell’implementazione
* [Introduzione all’utilizzo di Analysis Workspace](/help/analyze/analysis-workspace/home.md): immergiti direttamente in Adobe Analytics utilizzando la funzionalità principale dello strumento.
