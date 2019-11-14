---
description: Panoramica di come l’abilitazione dell’identificazione dei visitatori tra dispositivi influenzi i dati visualizzati nei rapporti.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Impatto dei dati sull'identificazione tra i visitatori dei visitatori
topic: Developer and implementation
uuid: 1db4d149-cd50-4b41-a850-988901f25051
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Impatto dei dati sull'identificazione tra i visitatori dei visitatori

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Fai riferimento alla documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud Device Co-op.

Panoramica di come l’abilitazione dell’identificazione dei visitatori tra dispositivi influenzi i dati visualizzati nei rapporti.

Per comprendere in che modo questa funzione influisce sulla raccolta dei dati, è utile comprendere i campi dati visitatore in un profilo visitatore:

| Campo dati | Descrizione |
|---|---|
| Cookie ID visitatore | ID generato automaticamente alla prima visita da un dispositivo o browser e memorizzato nel `s_vi` cookie. |
| Variabile ID visitatore | Facoltativo [!UICONTROL visitor ID] impostato utilizzando la `s.visitorID` variabile. Questo valore viene popolato dopo l’autenticazione di un utente e potrebbe corrispondere a un ID utilizzato dalla società per monitorare un utente su più canali di marketing digitale. |
| ID visitatore effettivo | L’ID effettivo [!UICONTROL visitor ID] è l’ID effettivo per il profilo utente. Questo valore viene impostato sul [!UICONTROL visitor ID] cookie o sulla [!UICONTROL visitor ID] variabile, se presente. |

