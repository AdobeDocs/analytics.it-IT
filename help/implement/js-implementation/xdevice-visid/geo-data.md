---
description: I dati di geolocalizzazione vengono registrati in base al primo hit della visita e non vengono modificati per una singola visita, indipendentemente dal dispositivo utilizzato.
keywords: Implementazione di Analytics
seo-description: I dati di geolocalizzazione vengono registrati in base al primo hit della visita e non vengono modificati per una singola visita, indipendentemente dal dispositivo utilizzato.
seo-title: Dati di geolocalizzazione
solution: Analytics
title: Dati di geolocalizzazione
topic: Sviluppatore e implementazione
uuid: 8449 bf 11-c 367-4698-a 73 e-f 6 cb 59 f 8 c 945
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Dati di geolocalizzazione

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori su dispositivi non è più consigliato. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

I dati di geolocalizzazione vengono registrati in base al primo hit della visita e non vengono modificati per una singola visita, indipendentemente dal dispositivo utilizzato.

Se un cliente sfoglia il sito dal proprio computer di casa e quindi da un dispositivo mobile entro 30 minuti, i dati della segmentazione non vengono modificati. Se utilizzi VISTA per compilare un evar con dati di segmentazione, si basa sull'indirizzo IP in ciascun hit. Questo potrebbe causare più valori di dati relativi alla geolocalizzazione se l'indirizzo IP cambia per la stessa visita.
