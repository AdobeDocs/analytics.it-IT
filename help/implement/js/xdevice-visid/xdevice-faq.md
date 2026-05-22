---
title: Domande frequenti sull’identificazione dei visitatori cross-device
description: Domande frequenti sull’identificazione dei visitatori cross-device
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
TQID: 'https://experienceleague.adobe.com/RBciiyfaq671zJ51QdJJDXcekFr-lfq0WPY0UAuWoVA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 80%

---

# Domande frequenti sull’identificazione dei visitatori cross-device

Domande frequenti sull’identificazione dei visitatori cross-device.

+++Qual è la differenza tra l’identificazione dei visitatori cross-device e Cross-Device Analytics?
L’identificazione dei visitatori cross-device utilizza la variabile `visitorID` per collegare diversi dispositivi, con alcune limitazioni importanti. Una delle maggiori limitazioni di questo metodo di identificazione è che gli hit non autenticati vengono isolati a meno che il dispositivo non sia già stato riconosciuto. Tali hit non autenticati possono portare a un conteggio in eccesso dei visitatori univoci.

Cross-Device Analytics è il più recente metodo Adobe per l’identificazione dei visitatori cross-device. Utilizza il servizio Experience Cloud ID e l’unione basata sui campi per unire retroattivamente le visite da diversi dispositivi. CDA richiede l’utilizzo di `setCustomerIDs` per determinare quali dispositivi vengono utilizzati dallo stesso visitatore.
+++

+++In che modo l’identificazione dei visitatori cross-device gestisce i segmenti?
L’identificazione dei visitatori cross-device tratta i segmenti in modo simile ad altre funzionalità. Esamina ogni singolo hit per vedere se corrisponde ai criteri del segmento e, in caso di corrispondenza, li include nei dati. I segmenti che utilizzano contenitori basati su visite e visitatori continuano a esaminare l’ID visitatore. Assicurati che la tua implementazione utilizzi la variabile `visitorID` per identificare in modo coerente i visitatori univoci per la segmentazione, ovunque possibile.
+++
