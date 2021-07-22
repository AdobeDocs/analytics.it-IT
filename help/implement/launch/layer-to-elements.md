---
title: Mappatura di oggetti del livello di dati su elementi di dati
description: Configura i tag da leggere dal livello dati.
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 10%

---

# Mappatura di oggetti del livello di dati su elementi di dati

Una volta che l’organizzazione ha stabilito e implementato un livello di dati sul sito, puoi mappare gli oggetti livello dati su elementi dati all’interno di tag.

>[!NOTE]
>Adobe Experience Platform Launch è stato riclassificato come una suite di tecnologie di raccolta dati nell’Experience Platform. Di conseguenza, sono state introdotte diverse modifiche terminologiche nella documentazione del prodotto. Consulta questo [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) come riferimento consolidato delle modifiche terminologiche.

## Prerequisiti

[Crea un livello](../prepare/data-layer.md) dati: Assicurati che sul sito esista un livello di dati. Anche se tecnicamente puoi mappare qualsiasi oggetto JavaScript o scollegare elementi CSS direttamente dalla pagina, Adobe consiglia questa pratica come ultima risorsa. Se il layout del sito cambia, i selettori CSS utilizzati nei tag smettono di funzionare, causando la perdita di dati.

## Utilizzare i tag per creare elementi dati

[Gli ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en) elementi dati sono componenti nell’interfaccia utente di raccolta dati che puoi utilizzare in tutto lo strumento. Puoi assegnare valori variabili nell’estensione Adobe Analytics utilizzando elementi dati.

1. Vai a [experience.adobe.com](https://experience.adobe.com) e accedi quando richiesto.
1. Select **[!UICONTROL Launch / Data Collection]**.
1. Fare clic su **[!UICONTROL Go to Launch / Data Collection]**, quindi selezionare **[!UICONTROL Tags]**.
1. Fai clic sulla proprietà tag desiderata.
1. Fai clic sulla scheda **[!UICONTROL Data Elements]** , quindi fai clic su **[!UICONTROL Add Data Element]**.

   ![crea elemento dati](assets/createelement.png)

1. Immetti un nome per l’elemento dati. Può essere una semplice etichetta che corrisponde a una variabile JavaScript nel livello dati che desideri monitorare.
1. Nel menu a discesa **[!UICONTROL Extension]** , seleziona **[!UICONTROL Core]**.
1. Nel menu a discesa **[!UICONTROL Data Element Type]** , seleziona **[!UICONTROL JavaScript Variable]**. A destra viene visualizzato un campo di testo che consente di inserire la variabile JavaScript da mappare a questo elemento dati.
1. Inserisci la variabile Javascript desiderata, in genere all’interno del livello dati. Ad esempio, se il livello dati dell’organizzazione corrisponde strettamente alla pratica consigliata da Adobe, un valore potrebbe essere `digitalData.page.pageInfo.pageName`. Puoi usare la console del browser per convalidare la sintassi e i valori delle variabili JavaScript.
1. Fai clic su **[!UICONTROL Save]**.

## Passaggi successivi

[Mappare gli elementi dati alle variabili](elements-to-variable.md) di Analytics: Assegna elementi dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in Analysis Workspace.
