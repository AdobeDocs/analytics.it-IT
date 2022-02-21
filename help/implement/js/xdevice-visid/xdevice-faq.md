---
title: Domande frequenti sull’identificazione dei visitatori tra dispositivi
description: Domande frequenti sull’identificazione dei visitatori tra dispositivi
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# Domande frequenti sull’identificazione dei visitatori tra dispositivi

Domande frequenti sull’identificazione dei visitatori tra dispositivi.

**Qual è la differenza tra l’identificazione dei visitatori tra dispositivi e Analytics tra dispositivi?**

L&#39;identificazione dei visitatori tra i dispositivi utilizza l&#39; `visitorID` per collegare i dispositivi, con diverse limitazioni principali. Una delle maggiori limitazioni di questo metodo di identificazione è che gli hit non autenticati vengono isolati a meno che il dispositivo non sia già stato riconosciuto. Questi hit non autenticati possono gonfiare i conteggi dei visitatori unici.

Cross-Device Analytics è il più recente metodo di identificazione dei visitatori tra dispositivi. Utilizza il servizio Experience Cloud ID e il grafico del dispositivo per unire retroattivamente le visite da diversi dispositivi. CDA richiede l&#39;utilizzo di `setCustomerIDs` per determinare quali dispositivi vengono utilizzati dallo stesso visitatore.

**In che modo l’identificazione dei visitatori tra dispositivi gestisce i segmenti?**

L’identificazione dei visitatori tra dispositivi tratta i segmenti in modo simile ad altre funzionalità. Esamina ogni singolo hit per vedere se corrisponde ai criteri del segmento e li include nei dati se corrisponde. I segmenti che utilizzano contenitori basati su visite e visitatori continuano a esaminare l’ID visitatore. Assicurati che l&#39;implementazione utilizzi `visitorID` per identificare in modo coerente i visitatori univoci per la segmentazione, ovunque possibile.
