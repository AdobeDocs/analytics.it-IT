---
title: Panoramica sulle origini dati
description: Importa dati in Adobe Analytics utilizzando file esterni.
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---

# Panoramica sulle origini dati

Le origini dati di Adobe Analytics ti consentono di importare ulteriori dati online o offline a scopo di reporting. Sono utili per comprendere gli aspetti della tua attività al di fuori del sito web e come interagiscono con il sito. Il flusso di lavoro generale per l’utilizzo delle origini dati è costituito dai passaggi seguenti:

1. La tua organizzazione raccoglie dati da altre origini. Alcuni esempi includono dati pre-clic, dati del call center o informazioni sulle transazioni avvenute al di fuori del sito.
1. I dati vengono formattati in modo tale che Adobe Analytics possa comprenderli utilizzando un file di testo delimitato da tabulazioni.
1. Caricare il file di testo in un Adobe del sito FTP fornito, insieme a un file `.fin` associato.
1. Adobe acquisisce il file di testo e visualizza tali dati insieme alle dimensioni e alle metriche raccolte sul sito.

Adobe offre due tipi generali di origini dati. Tutti i modelli di origine dati si basano su uno dei due tipi seguenti:

* **Origine dati di riepilogo**: consente di importare facilmente dati di alto livello in Adobe Analytics. Puoi specificare la marca temporale, il valore della variabile e le metriche associate. Tali metriche per ogni elemento dimensione vengono quindi aumentate di conseguenza. È utile se desideri visualizzare i dati offline e online uno accanto all’altro. Tuttavia, non collega tra loro i dati online e offline.
* **Origine dati ID transazione**: se un hit inviato da AppMeasurement e una riga origini dati contengono ID transazione corrispondenti, i valori di dimensione e metrica nell&#39;origine dati vengono aggiunti all&#39;hit.

**Le origini dati a elaborazione completa** non sono più offerte come tipo di origine dati al 25 marzo 2021. Per ulteriori informazioni, vedere [Annuncio sulla fine del ciclo di vita](full-processing-eol.md).

Adobe offre anche l&#39;[API origini dati](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), che consente di creare origini dati e caricare dati senza utilizzare l&#39;interfaccia utente del prodotto o un percorso FTP.

## Passaggi successivi

[Guida introduttiva alle origini dati](getting-started.md): carica un&#39;origine dati semplice in una suite di rapporti per lo sviluppo.
