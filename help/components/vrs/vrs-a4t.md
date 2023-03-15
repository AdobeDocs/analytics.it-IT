---
description: Considerazioni speciali quando si utilizzano suite di rapporti virtuali di A4T e Adobe Analytics
title: Suite di rapporti virtuali e Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Suite di rapporti virtuali e Analytics for Target (A4T)

Considera queste avvertenze quando utilizzi suite di rapporti virtuali nel contesto di Adobe Target:

* Non puoi inviare dati direttamente da Target a una suite di rapporti virtuale, ma solo a una suite di rapporti reale.
* Puoi creare rapporti sulle attività A4T all’interno di una suite di rapporti virtuale. Tuttavia, i dati A4T sono limitati alle righe che corrispondono al segmento della suite di rapporti virtuali (e a qualsiasi altro segmento applicato). Ad esempio, se hai creato una suite di rapporti virtuale per i clienti EMEA, i dati A4T in tale suite di rapporti virtuale riflettono solo i dati di Target per i clienti EMEA.
* Non puoi ripubblicare in Target i segmenti da una suite di rapporti virtuale per l’attivazione.
