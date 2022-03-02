---
title: Mappare gli elementi dati dei tag alle variabili Analytics
description: Assegna elementi dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
feature: Launch Implementation
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: f4b495b11bcbd55bc8448f2c9c09268547fb9750
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 4%

---


# Mappare gli elementi dati dei tag alle variabili Analytics

Una volta che hai un archivio di elementi dati tag, puoi assegnarli alle dimensioni di Analytics.

## Prerequisiti

[Mappatura di oggetti livello dati su elementi dati](layer-to-elements.md): Assicurati di comprendere gli elementi dei dati dei tag e di disporre di diversi elementi con cui lavorare.

[Creare un documento di progettazione della soluzione](../prepare/solution-design.md): Un documento di progettazione della soluzione è fondamentale per rimanere organizzati. Il seguente documento di progettazione della soluzione semplifica l&#39;assegnazione di elementi dati alle variabili di Analytics.

## Assegnare elementi dati alle variabili di Analytics

La pubblicazione di una libreria di tag dopo aver eseguito questi passaggi consente di utilizzare dimensioni personalizzate in Analysis Workspace. Puoi impostare le variabili di Analytics a livello globale o in singole regole.

### Imposta variabili globali

Le variabili globali sono ideali nei casi in cui desideri impostare valori variabili su tutte le pagine in cui esiste un elemento dati.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Fai clic sul pulsante [!UICONTROL Extensions tab], quindi fai clic su [!UICONTROL Configure] nell’estensione Adobe Analytics.
1. Fai clic sul pulsante [!UICONTROL Global variables] pannello a soffietto, che mostra l’interfaccia per assegnare variabili globali.

### Impostare le variabili nelle regole

Le variabili impostate nelle regole sono ideali nei casi in cui non desideri che le variabili siano impostate su ogni pagina. Puoi definire i criteri nella regola. Vedi [Regole](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) nella documentazione sui tag di Adobe Experience Platform.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Fai clic sul pulsante [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o creane una).
1. Fai clic sul pulsante [!UICONTROL Add] pulsante sotto [!UICONTROL Actions].
1. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] per impostare le variabili.
1. Fai clic sul pulsante ![Elemento dati](assets/data-element.png) a destra della variabile Analytics desiderata. La tua organizzazione [documento di progettazione della soluzione](../prepare/solution-design.md) determina la variabile di Analytics da utilizzare.
1. Seleziona l’elemento dati desiderato nella finestra modale. Fai clic su [!UICONTROL Select].
1. Il nome dell’elemento dati viene aggiunto al campo di testo circondato da `%` segni. Ad esempio, se hai denominato l’elemento dati &quot;Nome pagina&quot;, viene visualizzata la stringa `%Page name%` quando si assegna un elemento dati a una variabile.

>[!TIP]
>
>Puoi concatenare elementi dati nella stessa variabile. Ad esempio, se disponi di un elemento dati &quot;Hostname&quot; e di un elemento dati &quot;Pathname&quot;, puoi combinare entrambi in una singola variabile utilizzando `%Hostname%%Pathname%`.

## Passaggi successivi

[Variabili di pagina](../vars/page-vars/page-variables.md): Scopri le variabili a livello di pagina che puoi utilizzare nella tua implementazione per ottenere di più dalle dimensioni in Analysis Workspace.

[Variabili di configurazione](../vars/config-vars/configuration-variables.md): Scopri quali variabili di configurazione puoi utilizzare nella tua implementazione per sbloccare altre funzionalità in Adobe Analytics.
