---
title: Mappare gli elementi dati dei tag alle variabili Analytics
description: Assegna elementi dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/-eif71BEIQnPRQWSaXK5Wb5WL0rTROwRDDxzbUNL98I'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 15%

---

# Mappare gli elementi dati dei tag alle variabili Analytics

Una volta creato un archivio di elementi dati tag, puoi assegnarli alle dimensioni di Analytics.

## Prerequisiti

[Mappatura di oggetti del livello dati su elementi dati](layer-to-elements.md): assicurati di conoscere bene gli elementi dati dei tag e di averne diversi con cui lavorare.

[Crea un documento di progettazione della soluzione](../prepare/solution-design.md): un documento di progettazione della soluzione è fondamentale per rimanere organizzati. L’adesione al documento di progettazione della soluzione semplifica l’assegnazione di elementi dati alle variabili di Analytics.

## Assegnare elementi dati alle variabili di Analytics

La pubblicazione di una libreria di tag dopo aver seguito questi passaggi consente di utilizzare dimensioni personalizzate in Analysis Workspace. Puoi impostare le variabili di Analytics a livello globale o in singole regole.

### Imposta variabili globali

Le variabili globali sono ideali nei casi in cui desideri impostare i valori delle variabili su tutte le pagine in cui esiste l’elemento dati.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fai clic su [!UICONTROL Extensions tab], quindi su [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Fai clic sul pannello a soffietto [!UICONTROL Global variables], che mostra l&#39;interfaccia per assegnare le variabili globali.

### Impostare le variabili nelle regole

Le variabili impostate nelle regole sono ideali nei casi in cui non si desideri impostare le variabili su ogni pagina. Definisci i criteri nella regola. Vedi [Regole](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=it) nella documentazione dei tag di Adobe Experience Platform.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fai clic sulla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o creane una).
1. Fare clic sul pulsante [!UICONTROL Add] in [!UICONTROL Actions].
1. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su Imposta variabili.
1. Fai clic sull&#39;icona ![Elemento dati](assets/data-element.png) a destra della variabile Analytics desiderata. Il [documento di progettazione della soluzione](../prepare/solution-design.md) della tua organizzazione determina la variabile di Analytics da utilizzare.
1. Seleziona l’elemento dati desiderato nella finestra modale. Fai clic su [!UICONTROL Select].
1. Il nome dell&#39;elemento dati viene aggiunto al campo di testo racchiuso tra `%` segni. Ad esempio, se hai denominato l&#39;elemento dati &quot;Nome pagina&quot;, viene visualizzata la stringa `%Page name%` quando assegni un elemento dati a una variabile.

>[!TIP]
>
>Puoi concatenare elementi dati nella stessa variabile. Ad esempio, se si dispone di un elemento dati &quot;Hostname&quot; e di un elemento dati &quot;Pathname&quot;, è possibile combinarli entrambi in una singola variabile utilizzando `%Hostname%%Pathname%`.

## Passaggi successivi

[Variabili di pagina](../vars/page-vars/page-variables.md): scopri quali variabili a livello di pagina puoi utilizzare nell&#39;implementazione per sfruttare al meglio le dimensioni in Analysis Workspace.

[Variabili di configurazione](../vars/config-vars/configuration-variables.md): scopri le variabili di configurazione utilizzabili nell&#39;implementazione per sbloccare altre funzionalità in Adobe Analytics.
