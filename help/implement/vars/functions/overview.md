---
title: Funzioni e metodi
description: Scopri come utilizzare le funzioni e i metodi offerti da Adobe nella tua implementazione.
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Funzioni e metodi

Adobe offre diverse funzioni e metodi che puoi utilizzare nell’implementazione. Quando si fa riferimento a tali funzioni o metodi, questi eseguono operazioni comuni con un&#39;unica riga di codice.

Alcune di queste singole righe di codice appartengono alle seguenti categorie:

* **Chiamate di tracciamento**: i metodi più comuni e fondamentali in molte implementazioni. Includono i metodi [`t()`](t-method.md) e [`tl()`](tl-method.md).
* **Utilità AppMeasurement**: nelle versioni precedenti di AppMeasurement, le implementazioni dovevano scrivere il proprio codice per eseguire queste attività. Adobe fornisce questi metodi di utilità per semplificare queste attività comuni. Le utilità di AppMeasurement includono [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md) e [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registra funzioni**: puoi scrivere le tue funzioni e far sì che AppMeasurement le esegua automaticamente prima o dopo aver inviato una chiamata di tracciamento ad Adobe. Le variabili che rientrano in questa categoria sono [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md) e [`registerPostTrackCallback()`](registerposttrackcallback.md).
