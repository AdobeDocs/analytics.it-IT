---
title: Mappare gli elementi dei dati dei tag alle variabili di Analytics
description: Assegna elementi dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 3%

---

# Mappare gli elementi dei dati dei tag alle variabili di Analytics

Una volta che hai un archivio di elementi dati tag, puoi assegnarli alle dimensioni di Analytics.

>[!NOTE]
>Adobe Experience Platform Launch è stato riclassificato come una suite di tecnologie di raccolta dati nell’Experience Platform. Di conseguenza, sono state introdotte diverse modifiche terminologiche nella documentazione del prodotto. Consulta questo [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) come riferimento consolidato delle modifiche terminologiche.

## Prerequisiti

[Mappatura di oggetti livello dati su elementi](layer-to-elements.md) dati: Assicurati di comprendere gli elementi dei dati dei tag e di disporre di diversi elementi con cui lavorare.

[Crea un documento](../prepare/solution-design.md) di progettazione della soluzione: Un documento di progettazione della soluzione è fondamentale per rimanere organizzati. Il seguente documento di progettazione della soluzione semplifica l&#39;assegnazione di elementi dati alle variabili di Analytics.

## Assegnare elementi dati alle variabili di Analytics

La pubblicazione di una libreria di tag dopo aver eseguito questi passaggi consente di utilizzare dimensioni personalizzate in Analysis Workspace. Puoi impostare le variabili di Analytics a livello globale o in singole regole.

### Imposta variabili globali

Le variabili globali sono ideali nei casi in cui desideri impostare valori variabili su tutte le pagine in cui esiste un elemento dati.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Fai clic su [!UICONTROL Extensions tab], quindi fai clic su [!UICONTROL Configure] sotto l’estensione Adobe Analytics.
1. Fai clic sul pannello a soffietto [!UICONTROL Global variables] per visualizzare l’interfaccia per assegnare variabili globali.

### Impostare le variabili nelle regole

Le variabili impostate nelle regole sono ideali nei casi in cui non desideri che le variabili siano impostate su ogni pagina. Puoi definire i criteri nella regola. Consulta [Regole](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) nella documentazione sui tag di Adobe Experience Platform.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Fai clic sulla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o creane una).
1. Fare clic sul pulsante [!UICONTROL Add] in [!UICONTROL Actions].
1. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su Imposta variabili.
1. Fai clic sull&#39;icona ![Elemento dati](assets/data-element.png) a destra della variabile Analytics desiderata. Il documento di progettazione della soluzione [della tua organizzazione](../prepare/solution-design.md) determina quale variabile di Analytics utilizzare.
1. Seleziona l’elemento dati desiderato nella finestra modale. Fai clic su [!UICONTROL Select].
1. Il nome dell’elemento dati viene aggiunto al campo di testo circondato dai segni `%`. Ad esempio, se hai denominato l’elemento dati &quot;Nome pagina&quot;, quando assegni un elemento dati a una variabile visualizzerai la stringa `%Page name%` .

>[!TIP]
>
>Puoi concatenare elementi dati nella stessa variabile. Ad esempio, se disponi di un elemento dati &quot;Hostname&quot; e di un elemento dati &quot;Pathname&quot;, puoi combinare entrambi in una singola variabile utilizzando `%Hostname%%Pathname%`.

## Passaggi successivi

[Variabili](../vars/page-vars/page-variables.md) di pagina: Scopri le variabili a livello di pagina che puoi utilizzare nella tua implementazione per ottenere di più dalle dimensioni in Analysis Workspace.

[Variabili](../vars/config-vars/configuration-variables.md) di configurazione: Scopri quali variabili di configurazione puoi utilizzare nella tua implementazione per sbloccare altre funzionalità in Adobe Analytics.
