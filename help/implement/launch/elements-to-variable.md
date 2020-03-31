---
title: Mappatura degli elementi dei dati di Launch alle variabili Analytics
description: Assegnare elementi di dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
translation-type: tm+mt
source-git-commit: 6937d47e3cf980a21bec680cdbd2931a4a368221

---


# Mappatura degli elementi dei dati di Launch alle variabili Analytics

Dopo aver memorizzato un archivio degli elementi di dati in Adobe Experience Platform Launch, puoi assegnarli alle dimensioni di Analytics.

## Prerequisiti

[Mappare gli oggetti livello dati agli elementi](layer-to-elements.md)dati: Accertatevi di comprendere gli elementi dei dati in Launch e di disporre di diversi elementi con cui lavorare.

[Crea un documento](../prepare/solution-design.md)di progettazione della soluzione: Un documento di progettazione della soluzione è fondamentale per rimanere organizzati. Seguendo il documento di progettazione della soluzione, l&#39;assegnazione di elementi di dati alle variabili Analytics risulta semplificata.

## Assegnazione di elementi dati alle variabili di Analytics

La pubblicazione di una libreria in Launch dopo aver seguito questi passaggi consente di utilizzare dimensioni personalizzate in Analysis Workspace. Puoi impostare le variabili di Analytics a livello globale o in singole regole.

### Imposta variabili globali

Le variabili globali sono ideali nei casi in cui si desidera impostare valori variabili su tutte le pagine in cui esiste l’elemento dati.

1. Vai ad [Adobe Experience Platform Launch](https://launch.adobe.com) ed effettua l&#39;accesso, se richiesto.
1. Fare clic sulla proprietà Launch desiderata.
1. Fai clic su [!UICONTROL Extensions tab], quindi fai clic [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Fare clic sul [!UICONTROL Global variables] pannello a soffietto, che mostra l&#39;interfaccia per assegnare variabili globali.

### Impostazione di variabili nelle regole

Le variabili impostate nelle regole sono ideali nei casi in cui non si desidera impostare variabili su ogni pagina. Definite i criteri nella regola. Consulta [Regole](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html) nella guida utente di Adobe Experience Platform Launch.

1. Vai ad [Adobe Experience Platform Launch](https://launch.adobe.com) ed effettua l&#39;accesso, se richiesto.
1. Fare clic sulla proprietà Launch desiderata.
1. Fare clic sulla [!UICONTROL Rules] scheda, quindi sulla regola desiderata (o crearne una).
1. Click the [!UICONTROL Add] button under [!UICONTROL Actions].
1. Impostate il [!UICONTROL Extension] menu a discesa su Adobe Analytics e su [!UICONTROL Action Type] Imposta variabili.
1. Fai clic sull&#39;icona dell&#39;elemento ![](assets/data-element.png) Dati a destra della variabile Analytics desiderata. Il documento [di progettazione della](../prepare/solution-design.md) soluzione dell&#39;organizzazione stabilisce quale variabile Analytics usare.
1. Selezionare l&#39;elemento dati desiderato nella finestra modale. Fai clic su [!UICONTROL Select].
1. Il nome dell’elemento dati viene aggiunto al campo di testo circondato da `%` segni. Ad esempio, se l&#39;elemento dati è denominato &quot;Nome pagina&quot;, verrà visualizzata la stringa `%Page name%` quando si assegna un elemento dati a una variabile.

> [!TIP] È possibile concatenare elementi di dati nella stessa variabile. Ad esempio, se disponete di un elemento dati &quot;Nome host&quot; e di un elemento dati &quot;Nome percorso&quot;, potete combinare entrambi in una singola variabile utilizzando `%Hostname%%Pathname%`.

## Passaggi successivi

[Variabili](../vars/page-vars/page-variables.md)pagina: Scopri le variabili a livello di pagina che puoi utilizzare nell’implementazione per ottenere di più dalle dimensioni in Analysis Workspace.

[Variabili](../vars/config-vars/configuration-variables.md)di configurazione: Scopri le variabili di configurazione che puoi utilizzare nella tua implementazione per sbloccare ulteriori funzionalità in Adobe Analytics.
