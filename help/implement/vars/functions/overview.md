---
title: Funzioni e metodi
description: Scopri come utilizzare le funzioni e i metodi offerti da Adobe nella tua implementazione.
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
TQID: https://experienceleague.adobe.com/dKPvTPeRa7-SIFyIDU-7Mlob-3jsrfvhWmKeAveHGEc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 0%

---

# Funzioni e metodi

Adobe offre diverse funzioni e metodi che puoi utilizzare nell’implementazione. Quando si fa riferimento a tali funzioni o metodi, questi eseguono operazioni comuni con un&#39;unica riga di codice.

Alcune di queste singole righe di codice appartengono alle seguenti categorie:

* **Chiamate di tracciamento**: i metodi più comuni e fondamentali in molte implementazioni. Includono i metodi [`t()`](t-method.md) e [`tl()`](tl-method.md).
* **Utilità AppMeasurement**: nelle versioni precedenti di AppMeasurement, le implementazioni dovevano scrivere il proprio codice per eseguire queste attività. Adobe fornisce questi metodi di utilità per semplificare queste attività comuni. Le utilità di AppMeasurement includono [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md) e [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registra funzioni**: puoi scrivere le tue funzioni e far sì che AppMeasurement le esegua automaticamente prima o dopo aver inviato una chiamata di tracciamento ad Adobe. Le variabili che rientrano in questa categoria sono [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md) e [`registerPostTrackCallback()`](registerposttrackcallback.md).
