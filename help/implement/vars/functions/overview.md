---
title: Funzioni e metodi
description: Scopri come utilizzare le funzioni e i metodi offerti da Adobe nella tua implementazione.
feature: Variables
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 4%

---

# Funzioni e metodi

Adobe offre diverse funzioni e metodi che puoi utilizzare nell’implementazione. Quando si fa riferimento a queste funzioni o metodi, questi eseguono operazioni comuni con una singola riga di codice.

Alcune di queste singole righe di codice appartengono alle seguenti categorie:

* **Tracking delle chiamate**: I metodi più comuni e vitali in molte implementazioni. Includono [`t()`](t-method.md) e [`tl()`](tl-method.md) metodi.
* **Utility AppMeasurement**: Nelle versioni precedenti di AppMeasurement, le implementazioni dovevano scrivere il proprio codice per eseguire queste attività. L&#39;Adobe fornisce questi metodi di utilità per semplificare queste attività comuni. Le utility AppMeasurement includono [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md)e [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registrare le funzioni**: Puoi scrivere le tue funzioni e far sì che AppMeasurement le esegua automaticamente prima o dopo l’invio di una chiamata di tracciamento ad Adobe. Le variabili che rientrano in questa categoria sono [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md)e [`registerPostTrackCallback()`](registerposttrackcallback.md).
