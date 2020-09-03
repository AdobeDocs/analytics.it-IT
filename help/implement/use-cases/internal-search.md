---
title: Acquisisci termini di ricerca interni
description: Utilizzate una variabile personalizzata per acquisire i termini di ricerca interna.
translation-type: tm+mt
source-git-commit: 091e4b859addc1780d94d90c8b59748277890241
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---


# Acquisisci termini di ricerca interni

Il reporting della ricerca interna è integrato in molte organizzazioni e non è una dimensione standard con  Adobe Analytics. Tuttavia, con il minimo sforzo di implementazione, è possibile acquisire facilmente la generazione di report interni per i termini di ricerca.

## Prerequisiti

[Convalidare un’implementazione di sviluppo e pubblicarla in produzione](../launch/validate-publish-prod.md): Questa pagina presuppone che sia disponibile un&#39;implementazione di lavoro di base e che vengano visualizzate  richieste di immagini Adobe Analytics nel debugger del Adobe .

## Creare un eVar  per la ricerca interna

Segui l’amministratore [delle variabili di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione per creare un nuovo eVar  dedicato alla ricerca interna. Assegna al  eVar un nome facilmente riconoscibile (ad esempio &quot;Termine di ricerca interno&quot;) e registra il nuovo eVar  nel documento [di progettazione della](../prepare/solution-design.md)soluzione aziendale.

## Determinare la parola chiave di ricerca interna

La maggior parte delle ricerche interne utilizza le stringhe di query per trasmettere i dati delle parole chiave tra le pagine. Utilizzate la ricerca interna del sito e prendete nota dell&#39;URL nella pagina dei risultati della ricerca:

`https://example.com/search.html?q=kittens`

Se la ricerca interna del sito non utilizza l’URL, cerca il termine di ricerca in altre posizioni, come un livello dati o un cookie. Se non sei sicuro di dove trovare il termine di ricerca interno, collabora con il team di sviluppo del sito.

## Assegnazione del parametro della stringa di query a un elemento dati

Follow [Map data layer objects to data elements](../launch/layer-to-elements.md). Quando selezionate l’ **[!UICONTROL Data Element Type]**, selezionate **[!UICONTROL Query string parameter]** invece di **[!UICONTROL JavaScript Variable]**. Inserire il parametro della stringa di query desiderato (in genere `q`) nel campo di testo.

## Mappatura dell’elemento dati sul eVar 

Follow [Map Launch data elements to Analytics variables](../launch/elements-to-variable.md). Accertatevi di selezionare lo stesso eVar  creato nelle impostazioni della suite di rapporti.

## Avviare il processo di distribuzione di Launch

Follow [Deploy an Analytics implementation to a development environment](../launch/deploy-dev.md). Una volta confermato che funziona nell’ambiente di sviluppo, puoi [convalidare un’implementazione di sviluppo e pubblicarla in produzione](../launch/validate-publish-prod.md).

## Generazione di rapporti in Workspace.

Date un po&#39; di tempo alla vostra implementazione per raccogliere i dati, quindi potete iniziare a utilizzare la dimensione in  Analysis Workspace.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your AdobeID credentials.
2. Se non avete eseguito l&#39;accesso automatico a  Adobe Analytics, fate clic sull&#39;icona a 9 griglie in alto a destra e selezionate **[!UICONTROL Analytics]**.
3. Fate clic sulla **[!UICONTROL Workspace]** scheda e create un nuovo progetto.
4. Individuate il nome del eVar  creato in Dimension e trascinatelo nell’area di lavoro.
