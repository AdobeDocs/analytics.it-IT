---
title: Tipo di hit
description: Determina se l’hit è stato un hit in primo piano o in sfondo.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# Tipo di hit

La dimensione &#39;Hit type&#39; determina se un&#39;app mobile era in primo piano o in background quando l&#39;hit è stato inviato ai server di raccolta dati Adobe. Questa dimensione è pertinente solo alle suite di rapporti che contengono dati per le applicazioni mobili. I dati del browser raccolti tramite AppMeasurement segnalano sempre l’hit come &quot;Primo piano&quot;.

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni SDK mobili della versione 4.13.6 o successiva. Se non usi l’SDK per dispositivi mobili, tutti gli hit vengono elencati sotto il valore della dimensione &quot;In primo piano&quot;. Se è selezionata l’opzione &quot;Disattiva rapporti legacy e attribuzione per hit in background&quot;, gli hit in background verranno visualizzati solo nelle suite di rapporti [virtuali](../vrs/vrs-mobile-visit-processing.md).

## Valori dimensione

I valori delle dimensioni includono `"Foreground"` e `"Background"`. Qualsiasi hit che non è stato inviato in background di un’applicazione mobile appartiene al valore `"Foreground"` della dimensione. Qualsiasi hit inviato dove l’applicazione mobile era in background appartiene al valore della `"Background"` dimensione.
