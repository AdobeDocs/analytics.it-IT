---
title: Convalidare un'implementazione di sviluppo e pubblicare in produzione
description: Scopri come utilizzare i tag Adobe Experience Platform per distribuire Adobe Analytics nel tuo ambiente di produzione.
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 6%

---

# Convalidare un&#39;implementazione di sviluppo e pubblicare in produzione

Una volta effettuata la distribuzione dei tag in produzione, la tua organizzazione può iniziare a utilizzare Adobe Analytics per richiamare rapporti di base.

>[!NOTE]
>Adobe Experience Platform Launch è stato riclassificato come una suite di tecnologie di raccolta dati nell’Experience Platform. Di conseguenza, sono state introdotte diverse modifiche terminologiche nella documentazione del prodotto. Consulta questo [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) come riferimento consolidato delle modifiche terminologiche.

## Prerequisiti

[Implementare l&#39;implementazione di Analytics nell&#39;ambiente](deploy-dev.md) di sviluppo: Per seguire questa pagina, devi pubblicare un’implementazione di Analytics nel tuo ambiente di sviluppo.

## Convalidare l’implementazione di sviluppo tramite Experience Cloud Debugger

Il debugger di Experience Cloud è un plug-in Chrome che mostra tutti i tag di Experience Cloud presenti su una pagina.

1. Apri [Browser Web Chrome](https://www.google.com/chrome/) e vai a [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) su Chrome Web Store per installare l&#39;estensione.
2. Passa al sito web di sviluppo in cui sono stati implementati i tag.
3. Fai clic sull’icona di Adobe Experience Cloud Debugger in alto a destra di Chrome
4. Se tutto è implementato correttamente, dovresti vedere il contenuto in Adobe Analytics, tag e il servizio ID visitatore di Adobe Experience Cloud:

![debugger][assets/debugger.png]

## Implementare l&#39;implementazione di sviluppo per staging/prod

Dopo aver convalidato la visualizzazione dei dati, puoi inviare l’implementazione alla versione live del sito.

1. Vai a [experience.adobe.com](https://experience.adobe.com) e accedi quando richiesto.
1. Select **[!UICONTROL Launch / Data Collection]**.
1. Fare clic su **[!UICONTROL Go to Launch / Data Collection]**, quindi selezionare **[!UICONTROL Tags]**.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fai clic sulla scheda **[!UICONTROL Publishing]** e individua la libreria nella colonna di sviluppo.
1. Fai clic sul menu a discesa della libreria, quindi seleziona **[!UICONTROL Submit for Approval]**. Fai clic su **[!UICONTROL Submit]** nella finestra modale.
1. Fai nuovamente clic sull&#39;elenco a discesa della libreria (ora nella colonna Inviato) e seleziona **[!UICONTROL Build for Staging]**.
1. Dopo alcuni istanti, la luce gialla colorata della libreria diventa verde e indica una build corretta.
1. Fai nuovamente clic sul menu a discesa della libreria e seleziona **[!UICONTROL Approve for Publishing]**.
1. Fai nuovamente clic sull&#39;elenco a discesa della libreria (ora nella colonna [!UICONTROL Approved]) e seleziona **[!UICONTROL Build and Publish to Production]**.
1. Vai alla scheda Ambienti e fai clic su **[!UICONTROL Production Environment]**.
1. Copia l’intestazione di produzione e il codice a piè di pagina e invialo ai proprietari del sito web. Richiedi che implementino questo codice nell&#39;ambiente di produzione del tuo sito.

## Convalidare l’implementazione di produzione

Conferma di visualizzare i dati nella versione attiva del sito e avvia la raccolta dati ufficiale per Adobe Analytics.

1. Una volta confermato dai proprietari del sito web che hanno inviato il codice tag in produzione, accedi alla home page del sito web in Chrome e apri il [!UICONTROL Adobe Experience Cloud debugger].
2. Se tutto funziona, nell’ambiente di sviluppo dovresti visualizzare dati simili ai test. A questo punto, stai raccogliendo dati sul tuo sito e ora puoi iniziare a utilizzare Adobe Analytics per la generazione di rapporti.

## Risoluzione dei problemi

**Nel debugger non vengono visualizzati dati.**

Sul sito, apri la console per sviluppatori del browser (in genere F12). Osserva il codice sorgente della pagina e accertati che siano soddisfatte le seguenti condizioni:

* Non ci sono errori JavaScript nella console. Collabora con i proprietari del sito web della tua organizzazione per assicurarti che tutti gli errori JS siano risolti.
* Il codice di intestazione è implementato correttamente: Assicurati che il codice di intestazione sia all&#39;interno del tag `<head>` e che il file esista.
* La libreria AppMeasurement esiste: Passa direttamente all&#39;origine JS per assicurarti che il file JS contenga codice. In caso contrario, assicurati che ogni ambiente sia creato e che la libreria sia pubblicata nel rispettivo ambiente.
* Plug-in di interferenza: Alcuni plug-in di Chrome possono impedire l’attivazione delle richieste di immagini. Disattiva eventuali plug-in che potrebbero impedire l’invio di dati ai server di Adobe.

## Passaggi successivi

Ora che è impostata un’implementazione di base, il tuo ruolo all’interno dell’organizzazione può influenzare il percorso di cui desideri ulteriori informazioni:

* [Crea un documento](../prepare/solution-design.md) di progettazione della soluzione: Pianifica l’utilizzo delle variabili personalizzate, quindi includerle nell’implementazione
* [Introduzione all’utilizzo di Analysis Workspace](/help/analyze/analysis-workspace/home.md): Entra direttamente in Adobe Analytics utilizzando la funzionalità di punta dello strumento.
