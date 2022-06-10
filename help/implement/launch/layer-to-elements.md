---
title: Mappatura di oggetti del livello di dati su elementi di dati
description: Configura i tag da leggere dal livello dati.
feature: Launch Implementation
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 6%

---

# Mappatura di oggetti del livello di dati su elementi di dati

Una volta che l’organizzazione ha stabilito e implementato un livello di dati sul sito, puoi mappare gli oggetti livello dati su elementi dati all’interno di tag.

## Prerequisiti 

[Creare un livello di dati](../prepare/data-layer.md): Assicurati che sul sito esista un livello di dati. Anche se tecnicamente puoi mappare qualsiasi oggetto JavaScript o scollegare elementi CSS direttamente dalla pagina, Adobe consiglia questa pratica come ultima risorsa. Se il layout del sito cambia, i selettori CSS utilizzati nei tag smettono di funzionare, causando la perdita di dati.

## Utilizzare i tag per creare elementi dati

[Elementi dati](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en) sono componenti della raccolta dati di Adobe Experience Platform che puoi utilizzare in tutto lo strumento. Puoi assegnare valori variabili nell’estensione Adobe Analytics utilizzando elementi dati.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Fai clic sul pulsante **[!UICONTROL Data Elements]** scheda , quindi fai clic su **[!UICONTROL Add Data Element]**.

   ![crea elemento dati](assets/createelement.png)

1. Immetti un nome per l’elemento dati. Può essere una semplice etichetta che corrisponde a una variabile JavaScript nel livello dati che desideri monitorare.
1. Sotto la **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Core]**.
1. Sotto la **[!UICONTROL Data Element Type]** a discesa, seleziona **[!UICONTROL JavaScript Variable]**. A destra viene visualizzato un campo di testo che consente di inserire la variabile JavaScript da mappare a questo elemento dati.
1. Inserisci la variabile Javascript desiderata, in genere all’interno del livello dati. Ad esempio, se il livello dati dell’organizzazione corrisponde strettamente alla pratica consigliata da Adobe, potrebbe essere presente un valore `digitalData.page.pageInfo.pageName`. Puoi usare la console del browser per convalidare la sintassi e i valori delle variabili JavaScript.
1. Fai clic su **[!UICONTROL Save]**.

## Passaggi successivi

[Mappare gli elementi dati alle variabili di Analytics](elements-to-variable.md): Assegna elementi dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
