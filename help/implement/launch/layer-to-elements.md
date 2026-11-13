---
title: Mappatura di oggetti del livello dati su elementi di dati
description: Configura i tag per la lettura dal livello dati.
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 8%
---
# Mappatura di oggetti del livello dati su elementi di dati

Una volta che la tua organizzazione ha stabilito e implementato un livello dati sul sito, puoi mappare gli oggetti del livello dati agli elementi dati all’interno dei tag.

## Prerequisiti

[Crea un livello dati](../prepare/data-layer.md): assicurati che nel tuo sito esista un livello dati. Sebbene sia tecnicamente possibile mappare qualsiasi oggetto JavaScript o raschiare elementi CSS direttamente dalla pagina, Adobe consiglia questa procedura come ultima risorsa. Se il layout del sito cambia, i selettori CSS utilizzati nei tag cessano di funzionare, causando la perdita di dati.

## Utilizzare i tag per creare elementi dati

[Gli elementi dati](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=it) sono componenti di Raccolta dati di Adobe Experience Platform che puoi utilizzare in tutto lo strumento. Puoi assegnare valori di variabili nell’estensione Adobe Analytics utilizzando gli elementi dati.

Nei passaggi seguenti viene utilizzata l&#39;estensione [Adobe Client Data Layer](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/client-data-layer/overview), che deve essere installata nella proprietà tag.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Seleziona la proprietà tag desiderata.
1. Selezionare la scheda **[!UICONTROL Data Elements]**, quindi selezionare **[!UICONTROL Add Data Element]**.

   ![crea elemento dati](assets/createelement.png)

1. Immettere un nome per l&#39;elemento dati, ad esempio `Page name`.
1. Nell&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Adobe Client Data Layer]**.
1. Nell&#39;elenco a discesa **[!UICONTROL Data Element Type]**, selezionare **[!UICONTROL Data layer computed state]**.
1. In **[!UICONTROL Return value]**, seleziona **[!UICONTROL Specific path]**, quindi immetti il percorso del valore nel livello dati, ad esempio `page.name`. Per convalidare un percorso, esegui `adobeDataLayer.getState("page.name")` nella console del browser.
1. Seleziona **[!UICONTROL Save]**.

Utilizza questi elementi dati nelle regole che attivano l&#39;evento **[!UICONTROL Data layer push]** dell&#39;estensione, in modo che Data Layer abbia caricato e contenga i dati provenienti dal push. Vedi [Tipi di elementi dati](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/client-data-layer/data-element-types#computed-state).

### Livelli di dati basati su oggetti {#object-based}

Se il livello dati è un oggetto JavaScript, ad esempio un oggetto CEDDL `digitalData`, utilizzare il tipo di elemento dati **[!UICONTROL JavaScript Variable]** dell&#39;estensione **[!UICONTROL Core]**. Immettere il percorso del valore, ad esempio `digitalData.page.pageInfo.pageName`. Questo tipo di elemento dati non può leggere Adobe Client Data Layer, che memorizza i suoi dati in uno stato calcolato invece che nelle proprietà dell’oggetto.

## Passaggi successivi

[Mappatura di elementi dati su variabili di Analytics](elements-to-variable.md): assegna elementi dati a variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
