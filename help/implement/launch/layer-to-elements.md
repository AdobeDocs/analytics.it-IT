---
title: Mappatura di oggetti del livello di dati su elementi di dati
description: Configura i tag per la lettura dal livello dati.
feature: Launch Implementation
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 13%

---

# Mappatura di oggetti del livello di dati su elementi di dati

Una volta che la tua organizzazione ha stabilito e implementato un livello dati sul sito, puoi mappare gli oggetti del livello dati agli elementi dati all’interno dei tag.

## Prerequisiti

[Creare un livello di dati](../prepare/data-layer.md): assicurati che sul tuo sito esista un livello dati. Anche se tecnicamente puoi mappare qualsiasi oggetto JavaScript o raschiare elementi CSS direttamente dalla pagina, Adobe consiglia questa procedura come ultima risorsa. Se il layout del sito cambia, i selettori CSS utilizzati nei tag cessano di funzionare, causando la perdita di dati.

## Utilizzare i tag per creare elementi dati

[Elementi dati](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html) sono componenti di Raccolta dati di Adobe Experience Platform che puoi utilizzare all’interno dello strumento. Puoi assegnare valori di variabili nell’estensione Adobe Analytics utilizzando gli elementi dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fai clic su **[!UICONTROL Data Elements]** , quindi fai clic su **[!UICONTROL Add Data Element]**.

   ![creare un elemento dati](assets/createelement.png)

1. Immetti un nome per l’elemento dati. Può essere una semplice etichetta che corrisponde a una variabile JavaScript nel livello dati che desideri tracciare.
1. Sotto **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Core]**.
1. Sotto **[!UICONTROL Data Element Type]** a discesa, seleziona **[!UICONTROL JavaScript Variable]**. A destra viene visualizzato un campo di testo che consente di immettere la variabile JavaScript da mappare a questo elemento dati.
1. Immetti la variabile JavaScript desiderata, in genere all&#39;interno del livello dati. Ad esempio, se il livello dati della tua organizzazione corrisponde strettamente alla pratica consigliata da Adobe, un valore potrebbe essere `digitalData.page.pageInfo.pageName`. Puoi utilizzare la console del browser per convalidare la sintassi e i valori delle variabili JavaScript.
1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

## Passaggi successivi

[Mappare gli elementi dati alle variabili di Analytics](elements-to-variable.md): assegna elementi dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
