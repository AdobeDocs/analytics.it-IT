---
title: Mappatura di oggetti del livello di dati su elementi di dati
description: Configura Launch per la lettura dal livello dati.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 10%

---


# Mappatura di oggetti del livello di dati su elementi di dati

Una volta che l&#39;organizzazione ha stabilito e implementato un livello dati sul sito, è possibile mappare gli oggetti livello dati agli elementi dati all&#39;interno di Launch.

## Prerequisiti

[Create un livello](../prepare/data-layer.md)dati: Assicuratevi che sul sito esista un livello dati. Sebbene sia tecnicamente possibile mappare qualsiasi oggetto JavaScript o scollegare elementi CSS direttamente dalla pagina,  Adobe consiglia questa procedura come ultima risorsa. Se il layout del sito cambia, i selettori CSS utilizzati in Launch cessano di funzionare, causando la perdita di dati.

## Usare  Adobe Experience Platform Launch per creare elementi di dati

[Gli elementi](https://docs.adobe.com/content/help/it-IT/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) dati sono componenti di Launch utilizzabili in tutto lo strumento. È possibile assegnare valori variabili nell&#39;estensione  Adobe Analytics utilizzando gli elementi dati.

1. Accedete a [Adobe Experience Platform Launch](https://launch.adobe.com) e, se richiesto, effettuate l’accesso.
1. Fare clic sulla proprietà Launch desiderata.
1. Click the **[!UICONTROL Data Elements]** tab, then click **[!UICONTROL Add Data Element]**.

   ![crea elemento dati](assets/createelement.png)

1. Inserisci un nome per l’elemento dati. Può trattarsi di un&#39;etichetta semplice che corrisponde a una variabile JavaScript nel livello dati da monitorare.
1. Nel **[!UICONTROL Extension]** menu a discesa, selezionate **[!UICONTROL Core]**.
1. Nel **[!UICONTROL Data Element Type]** menu a discesa, selezionate **[!UICONTROL JavaScript Variable]**. A destra viene visualizzato un campo di testo che consente di inserire la variabile JavaScript da associare a questo elemento di dati.
1. Inserite la variabile Javascript desiderata, in genere all’interno del livello dati. Ad esempio, se il livello dati della tua organizzazione corrisponde  Adobe  pratica consigliata, potrebbe essere `digitalData.page.pageInfo.pageName`presente un valore. È possibile utilizzare la console del browser per convalidare la sintassi e i valori delle variabili JavaScript.
1. Fai clic su **[!UICONTROL Save]**.

## Passaggi successivi

[Mappatura degli elementi dati sulle variabili](elements-to-variable.md)di Analytics: Assegnare elementi di dati alle variabili di Analytics in modo da poterli utilizzare come dimensioni in  Analysis Workspace.
