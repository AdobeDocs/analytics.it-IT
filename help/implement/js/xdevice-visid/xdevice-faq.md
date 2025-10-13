---
title: Domande frequenti sull’identificazione dei visitatori cross-device
description: Domande frequenti sull’identificazione dei visitatori cross-device
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 90%

---

# Domande frequenti sull’identificazione dei visitatori cross-device

Domande frequenti sull’identificazione dei visitatori cross-device.

+++Qual è la differenza tra l’identificazione dei visitatori cross-device e Cross-Device Analytics?
L’identificazione dei visitatori cross-device utilizza la variabile `visitorID` per collegare diversi dispositivi, con alcune limitazioni importanti. Una delle maggiori limitazioni di questo metodo di identificazione è che gli hit non autenticati vengono isolati a meno che il dispositivo non sia già stato riconosciuto. Tali hit non autenticati possono portare a un conteggio in eccesso dei visitatori univoci.

Cross-Device Analytics è il più recente metodo Adobe per l’identificazione dei visitatori cross-device. Utilizza il servizio Experience Cloud ID e il grafo di dispositivi per unire retroattivamente le visite da diversi dispositivi. CDA richiede l’utilizzo di `setCustomerIDs` per determinare quali dispositivi vengono utilizzati dallo stesso visitatore.
+++

+++In che modo l’identificazione dei visitatori cross-device gestisce i segmenti?
L’identificazione dei visitatori cross-device tratta i segmenti in modo simile ad altre funzionalità. Esamina ogni singolo hit per vedere se corrisponde ai criteri del segmento e, in caso di corrispondenza, li include nei dati. I segmenti che utilizzano contenitori basati su visite e visitatori continuano a esaminare l’ID visitatore. Assicurati che la tua implementazione utilizzi la variabile `visitorID` per identificare in modo coerente i visitatori univoci per la segmentazione, ovunque possibile.
+++
