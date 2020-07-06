---
title: Mappatura degli elementi dei dati di Launch alle variabili Analytics
description: Assegnare elementi di dati  variabili Analytics in modo da poterli utilizzare come dimensioni in  Analysis Workspace.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 7%

---


# Mappatura degli elementi dei dati di Launch alle variabili Analytics

Dopo aver memorizzato un archivio di elementi di dati in  Adobe Experience Platform Launch, è possibile assegnarli  dimensioni Analytics.

## Prerequisiti

[Mappare gli oggetti livello dati agli elementi](layer-to-elements.md)dati: Accertatevi di comprendere gli elementi dei dati in Launch e di disporre di diversi elementi con cui lavorare.

[Crea un documento](../prepare/solution-design.md)di progettazione della soluzione: Un documento di progettazione della soluzione è fondamentale per rimanere organizzati. Seguendo il documento di progettazione della soluzione, l&#39;assegnazione di elementi di dati a  variabili Analytics risulta semplificata.

## Assegnazione di elementi dati alle variabili  Analytics

La pubblicazione di una libreria in Launch dopo aver eseguito questi passaggi consente di utilizzare dimensioni personalizzate in  Analysis Workspace. È possibile impostare  variabili Analytics a livello globale o in singole regole.

### Imposta variabili globali

Le variabili globali sono ideali nei casi in cui si desidera impostare valori variabili su tutte le pagine in cui esiste l’elemento dati.

1. Accedete a [Adobe Experience Platform Launch](https://launch.adobe.com) ed effettuate l&#39;accesso, se richiesto.
1. Fare clic sulla proprietà Launch desiderata.
1. Fate clic su [!UICONTROL Extensions tab], quindi fate clic [!UICONTROL Configure] sotto l’estensione Adobe  Analytics.
1. Fare clic sul [!UICONTROL Global variables] pannello a soffietto, che mostra l&#39;interfaccia per assegnare variabili globali.

### Impostazione di variabili nelle regole

Le variabili impostate nelle regole sono ideali nei casi in cui non si desidera impostare variabili su ogni pagina. Definite i criteri nella regola. Consultate [Regole](https://docs.adobe.com/content/help/it-IT/launch/using/reference/manage-resources/rules.html) nella guida utente di avvio del Adobe Experience Platform .

1. Accedete a [Adobe Experience Platform Launch](https://launch.adobe.com) ed effettuate l&#39;accesso, se richiesto.
1. Fare clic sulla proprietà Launch desiderata.
1. Fare clic sulla [!UICONTROL Rules] scheda, quindi sulla regola desiderata (o crearne una).
1. Click the [!UICONTROL Add] button under [!UICONTROL Actions].
1. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e su [!UICONTROL Action Type] Imposta variabili.
1. Fate clic sull&#39;icona dell&#39;elemento ![](assets/data-element.png) Dati a destra della variabile Analytics  desiderata. Il documento [di progettazione della](../prepare/solution-design.md) soluzione aziendale stabilisce  variabile Analytics da utilizzare.
1. Selezionare l&#39;elemento dati desiderato nella finestra modale. Fai clic su [!UICONTROL Select].
1. Il nome dell’elemento dati viene aggiunto al campo di testo circondato da `%` segni. Ad esempio, se l&#39;elemento dati è denominato &quot;Nome pagina&quot;, verrà visualizzata la stringa `%Page name%` quando si assegna un elemento dati a una variabile.

>[!TIP]
>
>È possibile concatenare elementi di dati nella stessa variabile. Ad esempio, se disponete di un elemento dati &quot;Nome host&quot; e di un elemento dati &quot;Nome percorso&quot;, potete combinare entrambi in una singola variabile utilizzando `%Hostname%%Pathname%`.

## Passaggi successivi

[Variabili](../vars/page-vars/page-variables.md)pagina: Scopri le variabili a livello di pagina che puoi utilizzare nell’implementazione per ottenere un maggior numero di informazioni dalle dimensioni in  Analysis Workspace.

[Variabili](../vars/config-vars/configuration-variables.md)di configurazione: Scoprite le variabili di configurazione che potete utilizzare nell&#39;implementazione per sbloccare ulteriori funzionalità in Adobe  Analytics.
