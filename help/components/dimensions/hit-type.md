---
title: Tipo di hit
description: Determina se l’hit è stato un hit in primo piano o in sfondo.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# Tipo di hit

La dimensione &#39;Hit type&#39; determina se un&#39;app mobile era in primo piano o in background quando l&#39;hit è stato inviato ai server di raccolta dati Adobe. Questa dimensione è pertinente solo alle suite di rapporti che contengono dati per le applicazioni mobili. I dati del browser raccolti tramite AppMeasurement segnalano sempre l’hit come &quot;Primo piano&quot;.

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni SDK mobili della versione 4.13.6 o successiva. Se non usi l’SDK per dispositivi mobili, puoi elencare tutti gli hit sotto l’elemento dimensione &quot;Primo piano&quot;. Se è selezionata l’opzione &quot;Disattiva rapporti legacy e attribuzione per hit in background&quot;, gli hit in background verranno visualizzati solo nelle suite di rapporti [virtuali](../vrs/vrs-mobile-visit-processing.md).

## Elementi dimensione

Gli elementi dimensione includono `"Foreground"` e `"Background"`. Qualsiasi hit che non è stato inviato sullo sfondo di un’applicazione mobile appartiene all’elemento `"Foreground"` dimensione. Qualsiasi hit inviato dove l’applicazione mobile era in background appartiene all’elemento `"Background"` dimensione.
