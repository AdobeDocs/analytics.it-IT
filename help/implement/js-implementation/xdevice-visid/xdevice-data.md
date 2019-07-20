---
description: Panoramica del modo in cui l'abilitazione dell'identificazione dei visitatori cross-device influisce sui dati visualizzati nei report.
keywords: Implementazione di Analytics
seo-description: Panoramica del modo in cui l'abilitazione dell'identificazione dei visitatori cross-device influisce sui dati visualizzati nei report.
seo-title: Impatto dei dati sull'identificazione dei visitatori cross-device
solution: Analytics
subtopic: Visitatori
title: Impatto dei dati sull'identificazione dei visitatori cross-device
topic: Sviluppatore e implementazione
uuid: 1 db 4 d 149-cd 50-4 b 41-a 850-988901 f 25051
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Impatto dei dati sull'identificazione dei visitatori cross-device

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori su dispositivi non è più consigliato. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Panoramica del modo in cui l'abilitazione dell'identificazione dei visitatori cross-device influisce sui dati visualizzati nei report.

Per capire in che modo questa funzione influisce sulla raccolta dati, è utile comprendere i campi dati dei visitatori in un profilo visitatore:

| Campo dati | Descrizione |
|---|---|
| ID visitatore cookie | ID generated automatically on the first visit from a device or browser and stored in the `s_vi` cookie. |
| Variabile ID visitatore | Optional [!UICONTROL visitor ID] that is set using the `s.visitorID` variable. Questo valore viene popolato dopo l'autenticazione e potrebbe corrispondere a un ID utilizzato dall'azienda per tenere traccia di un utente su più canali di marketing digitali. |
| ID visitatore effettivo | The effective [!UICONTROL visitor ID] is the actual ID for the user profile. This value is set to the [!UICONTROL visitor ID] cookie, or to the [!UICONTROL visitor ID] variable if one is provided. |

