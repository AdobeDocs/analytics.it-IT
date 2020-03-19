---
title: Funzioni e metodi
description: Scoprite come utilizzare le funzioni e i metodi offerti da Adobe nell'implementazione.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Funzioni e metodi

Adobe offre diverse funzioni e metodi utilizzabili per l’implementazione. Quando si fa riferimento a tali funzioni o metodi, questi eseguono operazioni comuni con un&#39;unica riga di codice.

Alcune di queste singole righe di codice appartengono alle seguenti categorie:

* **Tracciamento delle chiamate**: I metodi più comuni e vitali in molte implementazioni. Includono i metodi [`t()`](t-method.md) e [`tl()`](tl-method.md) .
* **Utility** AppMeasurement: Nelle versioni precedenti di AppMeasurement, le implementazioni dovevano scrivere il proprio codice per eseguire queste attività. Adobe fornisce questi metodi di utilità per semplificare le attività più comuni. Le utility AppMeasurement includono [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md)e [`Util.getQueryParam()`](util-getqueryparam.md).
* **Funzioni** di registrazione: Puoi scrivere le tue funzioni e far sì che AppMeasurement le esegua automaticamente prima o dopo l’invio di una chiamata di tracciamento ad Adobe. Le variabili che rientrano in questa categoria sono [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md)e [`registerPostTrackCallback()`](registerposttrackcallback.md).
