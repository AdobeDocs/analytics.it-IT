---
description: Puoi creare un segmento ogni volta che si verifica un'associazione per un cookie ID visitatore specificato.
keywords: Implementazione di Analytics
seo-description: Puoi creare un segmento ogni volta che si verifica un'associazione per un cookie ID visitatore specificato.
seo-title: Creare un segmento
solution: Analytics
title: Creare un segmento
topic: Sviluppatore e implementazione
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Creare un segmento

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Fai riferimento alla documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud Device Co-op.

Puoi creare un segmento ogni volta che si verifica un'associazione per un cookie ID visitatore specificato.

In base alla tabella [](/help/implement/js-implementation/xdevice-visid/visit-example.md)precedente, se hai creato un segmento con un numero di visita uguale a 9, includerebbe le chiamate al server 12 e 13. Anche attraverso la chiamata del server 11 faceva tecnicamente parte della stessa visita, i dati storici per quella chiamata al server non vengono modificati e il numero della visita rimane invariato.
