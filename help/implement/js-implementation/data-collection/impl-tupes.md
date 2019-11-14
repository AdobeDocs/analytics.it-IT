---
description: Queste informazioni sono destinate agli utenti avanzati che hanno esperienza sia nel reporting che nell'implementazione. Non tentare di modificare l'implementazione senza comprenderne le conseguenze. Se hai bisogno di modifiche all'implementazione, contatta l'Account Manager della tua organizzazione.
keywords: Analytics Implementation
solution: Analytics
title: Tracciare diversi tipi di implementazione
topic: Developer and implementation
uuid: a0a3229a-79a2-4dc2-b0be-4b8fac2efa3a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tracciare diversi tipi di implementazione

Queste informazioni sono destinate agli utenti avanzati che hanno esperienza sia nel reporting che nell'implementazione. Non tentare di modificare l'implementazione senza comprenderne le conseguenze. Se hai bisogno di modifiche all'implementazione, contatta l'Account Manager della tua organizzazione.

Se utilizzate più di un tipo di implementazione (ad esempio, richieste JavaScript e di immagini hardcoded), accertatevi che le seguenti variabili siano specificate e corrispondano tra loro:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (se si utilizza SSL)

Se ognuna di queste non corrisponde tra le diverse implementazioni, gli utenti possono essere tracciati come visitatori separati.
