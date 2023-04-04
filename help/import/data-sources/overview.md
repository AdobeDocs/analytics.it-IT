---
title: Panoramica delle origini dati
description: Importa dati in Adobe Analytics utilizzando file esterni.
source-git-commit: e32a7c85e2f0629c04bcd7ed0fa80ec1593bb6e8
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Panoramica delle origini dati

Le origini dati Adobe Analytics ti consentono di importare ulteriori dati online o offline per il reporting. Sono utili per comprendere gli aspetti della tua attività al di fuori del tuo sito web e come interagiscono con il tuo sito. Il flusso di lavoro generale da utilizzare per le origini dati consiste nei seguenti passaggi:

1. La tua organizzazione raccoglie dati da altre sorgenti. Gli esempi includono dati pre-clic, dati del call center o informazioni sulle transazioni che si sono verificate al di fuori del sito.
1. I dati vengono formattati in modo che Adobe Analytics possa comprendere utilizzando un file di testo delimitato da tabulazioni.
1. Puoi caricare il file di testo in un Adobe del sito FTP fornito, insieme a un `.fin` file.
1. In Adobe il file di testo viene acquisito e i dati vengono visualizzati insieme alle dimensioni e alle metriche raccolte sul sito.

Esistono due tipi generali di origini dati offerte da Adobe. Tutti i modelli di origine dati si basano su uno dei due tipi seguenti:

* **Riepilogo origine dati**: Fornisce un modo semplice per importare dati di alto livello in Adobe Analytics. Puoi specificare la marca temporale, il valore della variabile e le metriche associate. Tali metriche per ogni elemento dimensionale vengono quindi aumentate di conseguenza. È utile se desideri visualizzare i dati offline e online affiancati. Tuttavia, non collega insieme i dati online e offline.
* **Origine dati ID transazione**: Se un hit inviato da AppMeasurement e una riga di origini dati contengono ID di transazione corrispondenti, la dimensione e i valori di metrica nell’origine dati vengono aggiunti a tale hit.

**Origini dati di elaborazione completa** non sono più offerti come tipo di origine dati a partire dal 25 marzo 2021. Consulta la sezione [Annuncio di fine vita](full-processing-eol.md) per ulteriori informazioni.

Adobe offre anche [API origini dati](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), che consente di creare origini dati e caricare dati senza utilizzare l’interfaccia utente del prodotto o una posizione FTP.

## Passaggi successivi

[Guida introduttiva alle origini dati](getting-started.md): Carica una semplice origine dati in una suite di rapporti per lo sviluppo.
