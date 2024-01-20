---
title: Mappare gli elementi dati dei tag alle variabili Analytics
description: Assegna elementi dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: 2aef8de290399f234921b09cf094485fc06f1c24
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 13%

---


# Mappare gli elementi dati dei tag alle variabili Analytics

Una volta creato un archivio di elementi dati tag, puoi assegnarli alle dimensioni di Analytics.

## Prerequisiti

[Mappatura di oggetti del livello dati su elementi dati](layer-to-elements.md): accertati di conoscere bene gli elementi dati dei tag e di averne diversi con cui lavorare.

[Creare un documento di progettazione della soluzione](../prepare/solution-design.md): un documento di progettazione della soluzione è fondamentale per rimanere organizzati. L’adesione al documento di progettazione della soluzione semplifica l’assegnazione di elementi dati alle variabili di Analytics.

## Assegnare elementi dati alle variabili di Analytics

La pubblicazione di una libreria di tag dopo aver seguito questi passaggi consente di utilizzare dimensioni personalizzate in Analysis Workspace. Puoi impostare le variabili di Analytics a livello globale o in singole regole.

### Imposta variabili globali

Le variabili globali sono ideali nei casi in cui desideri impostare i valori delle variabili su tutte le pagine in cui esiste l’elemento dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fai clic su [!UICONTROL Extensions tab], quindi fai clic su [!UICONTROL Configure] nell’estensione Adobe Analytics.
1. Fai clic su [!UICONTROL Global variables] pannello a soffietto, che mostra l’interfaccia per assegnare le variabili globali.

### Impostare le variabili nelle regole

Le variabili impostate nelle regole sono ideali nei casi in cui non si desideri impostare le variabili su ogni pagina. Definisci i criteri nella regola. Consulta [Regole](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=it) nella documentazione sui tag di Adobe Experience Platform.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fai clic su [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o creane una).
1. Fai clic su [!UICONTROL Add] pulsante sotto [!UICONTROL Actions].
1. Imposta il [!UICONTROL Extension] in Adobe Analytics e nella sezione [!UICONTROL Action Type] per impostare le variabili.
1. Fai clic su ![Elemento dati](assets/data-element.png) a destra della variabile Analytics desiderata. Dell&#39;organizzazione [documento di progettazione della soluzione](../prepare/solution-design.md) Determina la variabile di Analytics da utilizzare.
1. Seleziona l’elemento dati desiderato nella finestra modale. Fai clic su [!UICONTROL Select] (Usa modello di attribuzione non predefinito).
1. Il nome dell’elemento dati viene aggiunto al campo di testo circondato da `%` segni. Ad esempio, se hai denominato l’elemento dati &quot;Nome pagina&quot;, viene visualizzata la stringa `%Page name%` quando si assegna un elemento dati a una variabile.

>[!TIP]
>
>Puoi concatenare elementi dati nella stessa variabile. Ad esempio, se disponi di un elemento dati &quot;Hostname&quot; e di un elemento dati &quot;Pathname&quot;, puoi combinarli entrambi in una singola variabile utilizzando `%Hostname%%Pathname%`.

## Passaggi successivi

[Variabili di pagina](../vars/page-vars/page-variables.md): scopri le variabili a livello di pagina utilizzabili nell’implementazione per ottenere di più dalle dimensioni in Analysis Workspace.

[Variabili di configurazione](../vars/config-vars/configuration-variables.md): scopri le variabili di configurazione utilizzabili nell’implementazione per sbloccare altre funzioni in Adobe Analytics.
