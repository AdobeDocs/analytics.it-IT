---
title: Panoramica su variabili, funzioni, metodi e plug-in
description: Scopri le variabili che puoi includere nei dati inviati al Adobe  per migliorare la generazione dei rapporti.
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---


# Panoramica su variabili, funzioni, metodi e plug-in

Analytics fornisce una serie di variabili per raccogliere i dati di Analytics. Le variabili in questa sezione sono suddivise in diverse sezioni:

* **Le variabili** di pagina sono valori generalmente utilizzati direttamente nel reporting. Le variabili di pagina comuni includono `props`, `eVars`e `events`.
* **Le variabili** di configurazione sono valori di impostazioni che consentono di garantire che i dati corretti raggiungano  Adobe. Le variabili di configurazione comuni includono `trackingServerSecure`, `charSet`e `linkTrackVars`. Le variabili di configurazione in genere non popolano gli elementi dimensione.
* **Funzioni e metodi** sono pezzi di codice che eseguono un&#39;attività specifica quando viene fatto riferimento. Le funzioni comuni includono `t()`, `tl()`e `clearVars()`.

## Variabili e metodi di implementazione

 Adobe offre diversi modi per implementare  Adobe Analytics. Ogni pagina offre una sezione su come implementare la variabile tramite Launch e AppMeasurement per JavaScript.

## Ordine delle operazioni

Le librerie AppMeasurement pubblicate da  Adobe Analytics seguono un ordine specifico quando si inviano dati a  Adobe. Se si eseguono queste attività in modo non ordinato, i dati possono essere incompleti.

1. Se il sito utilizza un livello dati, accertatevi che tutte le variabili applicabili siano compilate per prime. Per ulteriori informazioni, vedi [Livello](../prepare/data-layer.md) dati.
2. Utilizzate il livello dati per compilare le variabili di Analytics. Se si utilizza Launch, l&#39;attività viene eseguita facilmente utilizzando gli elementi dati, quindi assegnando l&#39;elemento dati a una variabile. Consulta Elementi [](https://docs.adobe.com/content/help/it-IT/launch/using/reference/manage-resources/data-elements.html) dati nella guida utente di Launch.
3. Chiama la funzione di tracciamento. La maggior parte delle librerie AppMeasurement utilizza il `t()` metodo, tuttavia alcuni SDK per dispositivi mobili vengono utilizzati `track()`. Quando viene chiamata la funzione di tracciamento, tutte le variabili supportate definite nell&#39;oggetto Analytics vengono inviate  Adobe sotto forma di richiesta di immagine.

## Caratteri non validi

I caratteri e le stringhe seguenti non sono mai consentiti nelle variabili JavaScript.

* Tab (`0x09`)
* Ritorno a capo (`0x0D`)
* Newline (`0x0A`)
* Tag HTML (ad esempio `<b></b>` o `&#153`)

Alcune variabili presentano limitazioni o requisiti di sintassi aggiuntivi. Ad esempio, la [`products`](page-vars/products.md) variabile riserva punti e virgola per delimitare prodotti e categorie separati.
