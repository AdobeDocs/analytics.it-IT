---
title: Funzioni e metodi
description: Scopri come utilizzare le funzioni e i metodi offerti da Adobe nella tua implementazione.
feature: Variables
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Funzioni e metodi

Adobe offre diverse funzioni e metodi che puoi utilizzare nell’implementazione. Quando si fa riferimento a tali funzioni o metodi, questi eseguono operazioni comuni con un&#39;unica riga di codice.

Alcune di queste singole righe di codice appartengono alle seguenti categorie:

* **Tracciamento delle chiamate**: i metodi più comuni e vitali in molte implementazioni di. Includono [`t()`](t-method.md) e [`tl()`](tl-method.md) metodi.
* **utility AppMeasurement**: nelle versioni precedenti di un AppMeasurement, le implementazioni dovevano scrivere il proprio codice per eseguire queste attività. Adobe fornisce questi metodi di utilità per semplificare queste attività comuni. Le utility di AppMeasurement includono [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md), e [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registra funzioni**: puoi scrivere le tue funzioni e far sì che AppMeasurement le esegua automaticamente prima o dopo l’invio di una chiamata di tracciamento ad Adobe. Le variabili che rientrano in questa categoria sono [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md), e [`registerPostTrackCallback()`](registerposttrackcallback.md).
