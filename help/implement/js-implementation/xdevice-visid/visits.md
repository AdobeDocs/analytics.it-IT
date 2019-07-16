---
description: Analytics conta una visita ogni volta che si verifica una chiamata al server con un numero di pagina visita pari a 1.
keywords: Implementazione di Analytics
seo-description: Analytics conta una visita ogni volta che si verifica una chiamata al server con un numero di pagina visita pari a 1.
seo-title: Visite
solution: Analytics
subtopic: Visitatori
title: Visite
topic: Sviluppatore e implementazione
uuid: 3035 be 8 f -6 adc -45 df-a 3 f 2-5 de 6 d 3 ed 99 ce
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Visite

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori su dispositivi non è più consigliato. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Analytics conta una visita ogni volta che si verifica una chiamata al server con un numero di pagina visita pari a 1.

If you look at the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), this occurred 4 times: at hits 1, 9, 11, and 12. Similar to visitors, this value returns to normal after the initial association because the [!UICONTROL Visit Page Number] is reset back to 1 due to a change in the effective [!UICONTROL visitor ID].
