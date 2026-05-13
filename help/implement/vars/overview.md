---
title: Panoramica di variabili, funzioni, metodi e plug-in
description: Scopri quali variabili puoi includere nei dati inviati ad Adobe per migliorare la generazione di rapporti.
keywords: appmeasurement,variabili,variabili,variabili,configurazione,pagina,implementazione
feature: Appmeasurement Implementation
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
role: Admin, Developer
TQID: https://experienceleague.adobe.com/J3bg65cq6Qjbv-Y-2sBaTmVHHniMpwudiM-YOM8VAhk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 417
ht-degree: 4%

---

# Panoramica di variabili, funzioni, metodi e plug-in

Analytics fornisce una serie di variabili per raccogliere i dati di Analytics. Le variabili in questa sezione sono suddivise in diverse sezioni:

* **Le variabili di pagina** sono valori generalmente utilizzati direttamente nel reporting. Le variabili di pagina comuni includono `props`, `eVars` e `events`.
* **Le variabili di configurazione** sono valori di impostazioni che consentono di assicurarsi che i dati corretti raggiungano Adobe. Le variabili di configurazione comuni includono `trackingServerSecure`, `charSet` e `linkTrackVars`. Le variabili di configurazione in genere non compilano gli elementi dimensione.
* **Le funzioni e i metodi** sono parti di codice che eseguono un&#39;attività specifica quando vi si fa riferimento. Le funzioni comuni includono `t()`, `tl()` e `clearVars()`.

## Variabili e metodi di implementazione

Adobe offre diversi modi per implementare Adobe Analytics. Ogni pagina offre una sezione su come implementare la variabile utilizzando Web SDK, l’estensione Adobe Analytics e AppMeasurement for JavaScript.


>[!BEGINSHADEBOX]

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurazione delle variabili](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/administration/manage-report-suites/configuring-variables-in-the-admin-console){target="_blank"} per un video demo.

>[!ENDSHADEBOX]


## Ordine delle operazioni

Le librerie AppMeasurement pubblicate da Adobe Analytics seguono un ordine specifico quando inviano dati ad Adobe. Se si eseguono queste attività fuori ordine, i dati possono essere incompleti.

1. Se il sito utilizza un livello di dati, assicurati che tutte le variabili applicabili siano compilate per prime. Ad esempio, si popola `adobeDataLayer.page.title` con il titolo della pagina. Consulta [Livello dati](../prepare/data-layer.md) per ulteriori informazioni.
2. Utilizza il livello dati per compilare le variabili di Analytics. <br/>Se si utilizzano i tag in Adobe Experience Platform, questa attività viene eseguita utilizzando gli elementi dati intermedi. Gli elementi dati vengono compilati con i valori del livello dati. Ad esempio, l&#39;elemento dati `Page Title` ottiene il valore dalla variabile del livello dati `adobeDataLayer.page.title`. <br/>È quindi possibile utilizzare l&#39;elemento dati per popolare le variabili di Analytics. Ad esempio `eVar4` ottiene il valore dall&#39;elemento dati `Page Title`. <br/>Per ulteriori informazioni, consulta [Elementi dati](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html), [Mappatura di oggetti livello dati su elementi dati](../launch/layer-to-elements.md) e [Mappatura di elementi dati tag su variabili Analytics](../launch/elements-to-variable.md)
3. Infine, chiama la funzione di tracciamento. La maggior parte delle librerie AppMeasurement utilizza il metodo `t()`, tuttavia alcuni SDK mobili utilizzano `track()`. Quando viene chiamata la funzione di tracciamento, tutte le variabili supportate definite nell’oggetto Analytics vengono inviate ad Adobe sotto forma di richiesta di immagine.

## Caratteri non validi

I seguenti caratteri e stringhe non sono mai consentiti nelle variabili JavaScript.

* Scheda (`0x09`)
* Ritorno a capo (`0x0D`)
* Nuova riga (`0x0A`)
* Tag HTML (ad esempio `<b></b>` o `&#153`)

Alcune variabili hanno limitazioni o requisiti di sintassi aggiuntivi. Ad esempio, la variabile [`products`](page-vars/products.md) riserva punti e virgola per delimitare prodotti e categorie separati.
