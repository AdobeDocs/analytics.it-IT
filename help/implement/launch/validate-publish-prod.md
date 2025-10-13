---
title: Convalidare un’implementazione di sviluppo e pubblicare in produzione
description: Scopri come utilizzare i tag Adobe Experience Platform per distribuire Adobe Analytics nell’ambiente di produzione.
feature: Tags
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
role: Admin, Developer
source-git-commit: e35210582e94037cf286b98e7e0a6b06040a8c6f
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 3%

---

# Convalidare un’implementazione di sviluppo e pubblicare in produzione

Una volta che la libreria di tag è stata inviata in produzione, la tua organizzazione può iniziare a utilizzare Adobe Analytics per richiamare rapporti di base.

## Prerequisiti

[Implementare Analytics nell&#39;ambiente di sviluppo](deploy-dev.md): per seguire questa pagina, è necessario pubblicare un&#39;implementazione di Analytics nell&#39;ambiente di sviluppo.

## Convalidare l’implementazione di sviluppo utilizzando Experience Cloud Debugger

Experience Cloud debugger è un’estensione che mostra tutti i tag Experience Cloud presenti in una pagina.

1. Installa l&#39;estensione per [Chrome](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) o Firefox.
2. Vai al tuo sito web di sviluppo su cui hai implementato i tag.
3. Fai clic sull’icona di Adobe Experience Cloud Debugger nel browser.
4. Se tutto è implementato correttamente, dovresti visualizzare il contenuto all’interno di Adobe Analytics, i tag e il servizio ID visitatore di Adobe Experience Cloud.

## Implementare l’implementazione di sviluppo in staging/produzione

Una volta verificato che i dati sono visibili, puoi inviare l’implementazione alla versione live del sito.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fai clic sulla scheda **[!UICONTROL Publishing]** e individua la libreria nella colonna Sviluppo.
1. Fare clic sull&#39;elenco a discesa della libreria, quindi selezionare **[!UICONTROL Submit for Approval]**. Fare clic su **[!UICONTROL Submit]** nella finestra modale.
1. Fare nuovamente clic sull&#39;elenco a discesa della libreria (ora nella colonna Inviato) e selezionare **[!UICONTROL Build for Staging]**.
1. Dopo alcuni istanti, la luce gialla colorata sulla libreria diventa verde, a indicare una build di successo.
1. Fare di nuovo clic sull&#39;elenco a discesa della libreria e selezionare **[!UICONTROL Approve for Publishing]**.
1. Fare nuovamente clic sull&#39;elenco a discesa della libreria (ora nella colonna [!UICONTROL Approved]) e selezionare **[!UICONTROL Build and Publish to Production]**.
1. Passare alla scheda Ambienti, quindi fare clic su **[!UICONTROL Production Environment]**.
1. Copia il codice di installazione di produzione e forniscilo ai proprietari del tuo sito web. Richiedi l&#39;implementazione di questo codice nell&#39;ambiente di produzione del tuo sito.

## Convalidare l’implementazione di produzione

Verifica di visualizzare i dati sulla versione live del sito e avvia la raccolta dati ufficiale per Adobe Analytics.

1. Dopo aver confermato dai proprietari del sito Web di aver inviato il codice tag alla produzione, accedi alla home page del sito Web in Chrome e apri [!UICONTROL Adobe Experience Cloud debugger].
2. Se tutto funziona, nell’ambiente di sviluppo dovrebbero essere visualizzati dati simili ai test. A questo punto, stai raccogliendo dati sul tuo sito e ora puoi iniziare a utilizzare Adobe Analytics per il reporting.

## Risoluzione dei problemi

**Nessun dato visualizzato nel debugger.**

Sul sito, apri la console per sviluppatori del browser (in genere F12). Osserva il codice sorgente della pagina e accertati che siano soddisfatte le seguenti condizioni:

* Nessun errore JavaScript nella console. Rivolgiti ai proprietari del sito web della tua organizzazione per assicurarti che tutti gli errori JS siano stati risolti.
* Il codice intestazione è implementato correttamente: verificare che il codice intestazione sia incluso nel tag `<head>` e che il file esista.
* Esiste già una libreria AppMeasurement: passa direttamente all’origine JS per assicurarti che il file JS contenga codice. In caso contrario, assicurati che ogni ambiente sia stato creato e che la libreria sia stata pubblicata nel rispettivo ambiente.
* Estensioni di interferenza: alcune estensioni, come ad blocker, possono impedire l’attivazione delle richieste di immagini. Disattiva le estensioni che potrebbero impedire l’invio dei dati ad Adobe.

## Passaggi successivi

Ora che è stata configurata un’implementazione di base, il tuo ruolo all’interno dell’organizzazione può influenzare il percorso su cui desideri saperne di più:

* [Crea un documento di progettazione della soluzione](../prepare/solution-design.md): crea un piano per l&#39;utilizzo delle variabili personalizzate, quindi includile nell&#39;implementazione
* [Inizia a utilizzare Analysis Workspace](/help/analyze/analysis-workspace/home.md): immergiti direttamente in Adobe Analytics utilizzando la funzionalità di punta dello strumento.
