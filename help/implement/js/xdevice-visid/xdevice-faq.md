---
title: Domande frequenti sull’identificazione dei visitatori tra dispositivi
description: Domande frequenti per l’identificazione dei visitatori su più dispositivi
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Domande frequenti sull’identificazione dei visitatori tra dispositivi

Domande frequenti per l’identificazione dei visitatori su più dispositivi.

**Qual è la differenza tra l&#39;identificazione dei visitatori cross-device e l&#39;analisi cross-device?**

L’identificazione dei visitatori tra dispositivi utilizza la `visitorID` variabile per collegare i dispositivi, con diverse limitazioni principali. Uno dei maggiori limiti di questo metodo di identificazione è che gli hit non autenticati sono isolati a meno che il dispositivo non sia già stato riconosciuto. Questi hit non autenticati possono gonfiare i conteggi dei visitatori univoci.

Analytics cross-device è l&#39;ultimo metodo di identificazione dei visitatori cross-device di Adobe. Utilizza il servizio Experience Cloud ID e il grafico del dispositivo per unire in modo retroattivo visite da diversi dispositivi. CDA richiede l’utilizzo della `setCustomerIDs` funzione per determinare quali dispositivi vengono utilizzati dallo stesso visitatore.

**In che modo vengono gestiti i segmenti di identificazione dei visitatori tra dispositivi?**

L&#39;identificazione dei visitatori tra dispositivi tratta i segmenti in modo simile ad altre funzionalità. Controlla ogni singolo hit per verificare se soddisfa i criteri del segmento e li include nei dati se corrisponde. I segmenti che utilizzano contenitori basati su visite e visitatori continuano a guardare l’ID visitatore. Assicurati che la tua implementazione utilizzi la `visitorID` variabile laddove possibile per identificare in modo coerente i visitatori univoci per la segmentazione.
