---
title: Panoramica di variabili, funzioni, metodi e plug-in
description: Scopri quali variabili puoi includere nei dati inviati ad Adobe per migliorare la generazione di rapporti.
keywords: appmeasurement,variabili,variabili,variabili,configurazione,pagina,implementazione
feature: Variables
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# Panoramica di variabili, funzioni, metodi e plug-in

Analytics fornisce una serie di variabili per raccogliere i dati di Analytics. Le variabili in questa sezione sono suddivise in diverse sezioni:

* **Variabili di pagina** sono valori che in genere vengono utilizzati direttamente nel reporting. Le variabili di pagina comuni includono `props`, `eVars`, e `events`.
* **Variabili di configurazione** sono valori di impostazioni che contribuiscono a garantire che i dati corretti raggiungano l’Adobe. Le variabili di configurazione comuni includono `trackingServerSecure`, `charSet`, e `linkTrackVars`. Le variabili di configurazione in genere non compilano gli elementi dimensione.
* **Funzioni e metodi** sono parti di codice che eseguono un&#39;attività specifica quando vi si fa riferimento. Le funzioni comuni includono `t()`, `tl()`, e `clearVars()`.

## Variabili e metodi di implementazione

Adobe offre diversi modi per implementare Adobe Analytics. Ogni pagina offre una sezione su come implementare la variabile utilizzando Web SDK, l’estensione Adobe Analytics e AppMeasurement per JavaScript.

Ecco un video sulla configurazione delle variabili in Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/28755/?quality=12)

## Ordine delle operazioni

Le librerie AppMeasurement pubblicate da Adobe Analytics seguono un ordine specifico quando inviano dati ad Adobe. Se si eseguono queste attività fuori ordine, i dati possono essere incompleti.

1. Se il sito utilizza un livello di dati, assicurati che tutte le variabili applicabili siano compilate per prime. Consulta [Livello dati](../prepare/data-layer.md) per ulteriori informazioni.
2. Utilizza il livello dati per compilare le variabili di Analytics. Se utilizzi i tag in Adobe Experience Platform, questa attività può essere facilmente eseguita utilizzando gli elementi dati e assegnando l’elemento dati a una variabile. Consulta [Elementi dati](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html).
3. Chiama la funzione di tracciamento. La maggior parte delle librerie AppMeasurement utilizzano `t()` , tuttavia l&#39;utilizzo di alcuni SDK per dispositivi mobili `track()`. Quando viene chiamata la funzione di tracciamento, tutte le variabili supportate definite nell’oggetto Analytics vengono inviate ad Adobe sotto forma di richiesta di immagine.

## Caratteri non validi

I seguenti caratteri e stringhe non sono mai consentiti nelle variabili JavaScript.

* Scheda (`0x09`)
* Ritorno a capo (`0x0D`)
* Nuova riga (`0x0A`)
* Tag HTML (ad es. `<b></b>` o `&#153`)

Alcune variabili hanno limitazioni o requisiti di sintassi aggiuntivi. Ad esempio, il [`products`](page-vars/products.md) la variabile riserva punti e virgola e virgole per delimitare prodotti e categorie separati.
