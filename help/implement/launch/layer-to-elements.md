---
title: Mappatura di oggetti del livello dati su elementi di dati
description: Configura i tag per la lettura dal livello dati.
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 13%

---

# Mappatura di oggetti del livello dati su elementi di dati

Una volta che la tua organizzazione ha stabilito e implementato un livello dati sul sito, puoi mappare gli oggetti del livello dati agli elementi dati all’interno dei tag.

## Prerequisiti

[Crea un livello dati](../prepare/data-layer.md): assicurati che nel tuo sito esista un livello dati. Sebbene sia tecnicamente possibile mappare qualsiasi oggetto JavaScript o raschiare elementi CSS direttamente dalla pagina, Adobe consiglia questa procedura come ultima risorsa. Se il layout del sito cambia, i selettori CSS utilizzati nei tag cessano di funzionare, causando la perdita di dati.

## Utilizzare i tag per creare elementi dati

[Gli elementi dati](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html) sono componenti di Raccolta dati di Adobe Experience Platform che puoi utilizzare in tutto lo strumento. Puoi assegnare valori di variabili nell’estensione Adobe Analytics utilizzando gli elementi dati.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fare clic sulla scheda **[!UICONTROL Data Elements]**, quindi su **[!UICONTROL Add Data Element]**.

   ![crea elemento dati](assets/createelement.png)

1. Immetti un nome per l’elemento dati. Può essere una semplice etichetta che corrisponde a una variabile JavaScript nel livello dati che desideri tracciare.
1. Nell&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Core]**.
1. Nell&#39;elenco a discesa **[!UICONTROL Data Element Type]**, selezionare **[!UICONTROL JavaScript Variable]**. A destra viene visualizzato un campo di testo che consente di immettere la variabile JavaScript da mappare a questo elemento dati.
1. Immetti la variabile JavaScript desiderata, in genere all&#39;interno del livello dati. Ad esempio, se il livello dati della tua organizzazione corrisponde alla pratica consigliata di Adobe, un valore potrebbe essere `digitalData.page.pageInfo.pageName`. Puoi utilizzare la console del browser per convalidare la sintassi e i valori delle variabili JavaScript.
1. Fai clic su **[!UICONTROL Save]**.

## Passaggi successivi

[Mappatura di elementi dati su variabili di Analytics](elements-to-variable.md): assegna elementi dati a variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
