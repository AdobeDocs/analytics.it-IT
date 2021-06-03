---
title: Mappatura di oggetti del livello di dati su elementi di dati
description: Configura Launch per leggere dal livello dati.
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 6%

---

# Mappatura di oggetti del livello di dati su elementi di dati

Una volta che l’organizzazione ha stabilito e implementato un livello di dati sul sito, puoi mappare gli oggetti livello dati su elementi dati in Launch.

## Prerequisiti

[Crea un livello](../prepare/data-layer.md) dati: Assicurati che sul sito esista un livello di dati. Anche se tecnicamente puoi mappare qualsiasi oggetto JavaScript o scollegare elementi CSS direttamente dalla pagina, Adobe consiglia questa pratica come ultima risorsa. Se il layout del sito cambia, i selettori CSS utilizzati in Launch smettono di funzionare, causando la perdita di dati.

## Utilizzare Adobe Experience Platform Launch per creare elementi dati

[Gli ](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) elementi dati sono componenti in Launch che puoi utilizzare in tutto lo strumento. Puoi assegnare valori variabili nell’estensione Adobe Analytics utilizzando elementi dati.

1. Vai a [Adobe Experience Platform Launch](https://launch.adobe.com) e, se richiesto, accedi.
1. Fai clic sulla proprietà Launch desiderata.
1. Fai clic sulla scheda **[!UICONTROL Data Elements]** , quindi fai clic su **[!UICONTROL Add Data Element]**.

   ![crea elemento dati](assets/createelement.png)

1. Immetti un nome per l’elemento dati. Può essere una semplice etichetta che corrisponde a una variabile JavaScript nel livello dati che desideri monitorare.
1. Nel menu a discesa **[!UICONTROL Extension]** , seleziona **[!UICONTROL Core]**.
1. Nel menu a discesa **[!UICONTROL Data Element Type]** , seleziona **[!UICONTROL JavaScript Variable]**. A destra viene visualizzato un campo di testo che consente di inserire la variabile JavaScript da mappare a questo elemento dati.
1. Inserisci la variabile Javascript desiderata, in genere all’interno del livello dati. Ad esempio, se il livello dati dell’organizzazione corrisponde strettamente alla pratica consigliata da Adobe, un valore potrebbe essere `digitalData.page.pageInfo.pageName`. Puoi usare la console del browser per convalidare la sintassi e i valori delle variabili JavaScript.
1. Fai clic su **[!UICONTROL Save]**.

## Passaggi successivi

[Mappare gli elementi dati alle variabili](elements-to-variable.md) di Analytics: Assegna elementi dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
