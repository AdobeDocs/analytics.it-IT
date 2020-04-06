---
title: dc
description: Variabile ritirata che consente di determinare quale centro dati utilizzare.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# dc

>[!IMPORTANT] Questa variabile è ritirata. Usa [`trackingServer`](trackingserver.md) invece.

Nelle versioni precedenti di Adobe Analytics, Adobe aveva richiesto di specificare a quale centro dati si desidera inviare i dati. L&#39;invio di hit al centro dati errato causava la perdita di dati.

Adobe ha migliorato questa esperienza consentendo a qualsiasi implementazione di inviare hit `sc.omtrdc.net`. La specifica del data center non è più necessaria.
