---
title: Panoramica di variabili, funzioni, metodi e plug-in
description: Scopri quali variabili puoi includere nei dati inviati ad Adobe per migliorare il reporting.
keywords: appmeasurement,variabili,vars,configurazione,pagina,implementazione
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Panoramica di variabili, funzioni, metodi e plug-in

Analytics fornisce una serie di variabili per raccogliere i dati di Analytics. Le variabili in questa sezione sono suddivise in diverse sezioni:

* **Le** variabili di pagina sono valori generalmente utilizzati direttamente nel reporting. Le variabili di pagina comuni includono `props`, `eVars` e `events`.
* **Le** variabili di configurazione sono valori di impostazione che consentono di garantire che i dati corretti raggiungano l&#39;Adobe. Le variabili di configurazione comuni includono `trackingServerSecure`, `charSet` e `linkTrackVars`. Le variabili di configurazione in genere non compilano gli elementi dimensionali.
* **Funzioni e** metodi sono parti di codice che eseguono un&#39;attività specifica quando viene fatto riferimento a tale attività. Le funzioni comuni includono `t()`, `tl()` e `clearVars()`.

## Variabili e metodi di implementazione

Adobe offre diversi modi per implementare Adobe Analytics. Ogni pagina offre una sezione su come implementare la variabile utilizzando Launch e AppMeasurement per JavaScript.

## Ordine delle operazioni

Le librerie AppMeasurement pubblicate da Adobe Analytics seguono un ordine specifico quando si inviano dati ad Adobe. Se esegui queste attività in modo errato, i dati possono essere incompleti.

1. Se il sito utilizza un livello di dati, assicurati che tutte le variabili applicabili siano prima popolate. Per ulteriori informazioni, consulta [Livello dati](../prepare/data-layer.md) .
2. Utilizza il livello dati per compilare le variabili di Analytics. Se utilizzi Launch, questa attività viene facilmente eseguita utilizzando elementi dati, quindi assegnando l’elemento dati a una variabile. Consulta [Elementi dati](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/data-elements.html) nella guida utente di Launch.
3. Chiama la funzione di tracciamento. La maggior parte delle librerie AppMeasurement utilizza il metodo `t()` , tuttavia alcuni SDK per dispositivi mobili utilizzano `track()`. Quando viene chiamata la funzione di tracciamento, tutte le variabili supportate definite nell&#39;oggetto Analytics vengono inviate ad Adobe sotto forma di richiesta di immagine.

## Caratteri non validi

I seguenti caratteri e stringhe non sono mai consentiti nelle variabili JavaScript.

* Scheda (`0x09`)
* Ritorno a capo (`0x0D`)
* Newline (`0x0A`)
* Tag HTML (ad esempio `<b></b>` o `&#153`)

Alcune variabili presentano limitazioni o requisiti di sintassi aggiuntivi. Ad esempio, la variabile [`products`](page-vars/products.md) riserva punti e virgola per delimitare prodotti e categorie separati.
