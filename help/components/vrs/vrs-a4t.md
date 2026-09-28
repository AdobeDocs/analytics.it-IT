---
description: Considerazioni speciali quando si utilizzano suite di rapporti virtuali di A4T e Adobe Analytics
title: Suite di rapporti virtuali e Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
TQID: 'https://experienceleague.adobe.com/SIJbZiyHFtGFUrlno5-Kov3kDP4QOXREW00jyDsIGFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%
---
# Suite di rapporti virtuali e Analytics for Target (A4T)

Considera queste avvertenze quando utilizzi suite di rapporti virtuali nel contesto di Adobe Target:

* Non puoi inviare dati direttamente da Target a una suite di rapporti virtuale, ma solo a una suite di rapporti reale.
* Puoi creare rapporti sulle attività A4T all’interno di una suite di rapporti virtuale. Tuttavia, i dati A4T sono limitati alle righe che corrispondono al segmento della suite di rapporti virtuali (e a qualsiasi altro segmento applicato). Ad esempio, se hai creato una suite di rapporti virtuale per i clienti EMEA, i dati A4T in tale suite di rapporti virtuale riflettono solo i dati di Target per i clienti EMEA.
* Non puoi ripubblicare in Target i segmenti da una suite di rapporti virtuale per l’attivazione.
