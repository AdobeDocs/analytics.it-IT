---
title: Domande frequenti sull’identificazione dei visitatori tra dispositivi
description: Domande frequenti per l’identificazione dei visitatori su più dispositivi
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---


# Domande frequenti sull’identificazione dei visitatori tra dispositivi

Domande frequenti per l’identificazione dei visitatori su più dispositivi.

**Qual è la differenza tra l&#39;identificazione dei visitatori cross-device e l&#39;analisi cross-device?**

L&#39;identificazione dei visitatori su più dispositivi utilizza la variabile `visitorID` per collegare i dispositivi, con diverse limitazioni importanti. Uno dei maggiori limiti di questo metodo di identificazione è che gli hit non autenticati sono isolati a meno che il dispositivo non sia già stato riconosciuto. Questi hit non autenticati possono gonfiare i conteggi dei visitatori univoci.

Analytics cross-device è  Adobe  più recente metodo di identificazione dei visitatori cross-device. Utilizza il servizio ID Experience Cloud  e il grafico del dispositivo per unire in modo retroattivo visite da diversi dispositivi. CDA richiede l&#39;utilizzo della funzione `setCustomerIDs` per determinare quali dispositivi vengono utilizzati dallo stesso visitatore.

**In che modo vengono gestiti i segmenti di identificazione dei visitatori tra dispositivi?**

L&#39;identificazione dei visitatori tra dispositivi tratta i segmenti in modo simile ad altre funzionalità. Controlla ogni singolo hit per verificare se soddisfa i criteri del segmento e li include nei dati se corrisponde. I segmenti che utilizzano contenitori basati su visite e visitatori continuano a guardare l’ID visitatore. Assicurati che la tua implementazione utilizzi la variabile `visitorID` laddove possibile per identificare in modo coerente i visitatori univoci per la segmentazione.
