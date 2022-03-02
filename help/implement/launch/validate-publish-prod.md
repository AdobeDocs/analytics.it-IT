---
title: Convalidare un'implementazione di sviluppo e pubblicare in produzione
description: Scopri come utilizzare i tag Adobe Experience Platform per distribuire Adobe Analytics nel tuo ambiente di produzione.
feature: Launch Implementation
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 7cae63a63b7047c1907ebe4c4f25f38b6b4237d4
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 5%

---

# Convalidare un&#39;implementazione di sviluppo e pubblicare in produzione

Una volta effettuata la distribuzione dei tag in produzione, la tua organizzazione può iniziare a utilizzare Adobe Analytics per richiamare rapporti di base.

## Prerequisiti

[Implementazione di Analytics nell’ambiente di sviluppo](deploy-dev.md): Per seguire questa pagina, devi pubblicare un’implementazione di Analytics nel tuo ambiente di sviluppo.

## Convalidare l’implementazione di sviluppo tramite Experience Cloud Debugger

Experience Cloud Debugger è un’estensione che mostra tutti i tag Experienci Cloud presenti in una pagina.

1. Installa l&#39;estensione per [Chrome](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) o [Firefox](https://addons.mozilla.org/it/firefox/addon/adobe-experience-platform-dbg/).
2. Passa al sito web di sviluppo in cui sono stati implementati i tag.
3. Fai clic sull’icona di Adobe Experience Cloud Debugger nel browser.
4. Se tutto è implementato correttamente, dovresti vedere il contenuto in Adobe Analytics, tag e il servizio ID visitatore di Adobe Experience Cloud.

## Implementare l&#39;implementazione di sviluppo per staging/prod

Dopo aver convalidato la visualizzazione dei dati, puoi inviare l’implementazione alla versione live del sito.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fai clic sul pulsante **[!UICONTROL Publishing]** individua la libreria nella colonna di sviluppo .
1. Fai clic sul menu a discesa della libreria, quindi seleziona **[!UICONTROL Submit for Approval]**. Fai clic su **[!UICONTROL Submit]** nella finestra modale.
1. Fai nuovamente clic sull&#39;elenco a discesa della libreria (ora nella colonna Inviato) e seleziona **[!UICONTROL Build for Staging]**.
1. Dopo alcuni istanti, la luce gialla colorata della libreria diventa verde e indica una build corretta.
1. Fai nuovamente clic sul menu a discesa della libreria e seleziona **[!UICONTROL Approve for Publishing]**.
1. Fai di nuovo clic sul menu a discesa della libreria (ora nella [!UICONTROL Approved] e seleziona **[!UICONTROL Build and Publish to Production]**.
1. Vai alla scheda Ambienti e fai clic su **[!UICONTROL Production Environment]**.
1. Copia il codice di installazione di produzione e forniscilo ai proprietari del sito web. Richiedi che implementino questo codice nell&#39;ambiente di produzione del tuo sito.

## Convalidare l’implementazione di produzione

Conferma di visualizzare i dati nella versione attiva del sito e avvia la raccolta dati ufficiale per Adobe Analytics.

1. Dopo aver confermato dai proprietari del sito web che hanno inviato il codice tag in produzione, accedi alla home page del tuo sito web in Chrome e apri il [!UICONTROL Adobe Experience Cloud debugger].
2. Se tutto funziona, nell’ambiente di sviluppo dovresti visualizzare dati simili ai test. A questo punto, stai raccogliendo dati sul tuo sito e ora puoi iniziare a utilizzare Adobe Analytics per la generazione di rapporti.

## Risoluzione dei problemi

**Nel debugger non vengono visualizzati dati.**

Sul sito, apri la console per sviluppatori del browser (in genere F12). Osserva il codice sorgente della pagina e accertati che siano soddisfatte le seguenti condizioni:

* Non ci sono errori JavaScript nella console. Collabora con i proprietari del sito web della tua organizzazione per assicurarti che tutti gli errori JS siano risolti.
* Il codice di intestazione è implementato correttamente: Assicurati che il codice di intestazione sia all&#39;interno della `<head>` e che il file esista.
* La libreria AppMeasurement esiste: Passa direttamente all&#39;origine JS per assicurarti che il file JS contenga codice. In caso contrario, assicurati che ogni ambiente sia creato e che la libreria sia pubblicata nel rispettivo ambiente.
* Estensioni di interferenza: Alcune estensioni, come ad blocker, possono impedire l&#39;attivazione delle richieste di immagini. Disattiva le estensioni che potrebbero impedire l&#39;invio di dati ad Adobe.

## Passaggi successivi

Ora che è impostata un’implementazione di base, il tuo ruolo all’interno dell’organizzazione può influenzare il percorso di cui desideri ulteriori informazioni:

* [Creare un documento di progettazione della soluzione](../prepare/solution-design.md): Pianifica l’utilizzo delle variabili personalizzate, quindi includerle nell’implementazione
* [Introduzione all’utilizzo di Analysis Workspace](/help/analyze/analysis-workspace/home.md): Entra direttamente in Adobe Analytics utilizzando la funzionalità di punta dello strumento.
