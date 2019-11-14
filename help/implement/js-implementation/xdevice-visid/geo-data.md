---
description: I dati di segmentazione geografica vengono registrati in base al primo hit della visita e non vengono modificati per una singola visita, indipendentemente dal dispositivo utilizzato.
keywords: Analytics Implementation
solution: Analytics
title: Dati di geo-segmentazione
topic: Developer and implementation
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Dati di geo-segmentazione

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Fai riferimento alla documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud Device Co-op.

I dati di segmentazione geografica vengono registrati in base al primo hit della visita e non vengono modificati per una singola visita, indipendentemente dal dispositivo utilizzato.

Se un cliente accede al sito dal computer di casa e successivamente da un dispositivo mobile entro 30 minuti, i dati di segmentazione geografica non vengono modificati. Se si utilizza VISTA per compilare un eVar con dati di segmentazione geografica, questo si basa sull'indirizzo IP di ogni hit. Ciò potrebbe causare più valori di dati di segmentazione geografica se l’indirizzo IP cambia per la stessa visita.
