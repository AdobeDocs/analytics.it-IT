---
title: Tracciare diversi tipi di implementazione
description: Utilizza diversi tipi di implementazione e monitora i visitatori in modo semplice tra loro.
feature: Implementation Basics
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 9%

---

# Tracciare diversi tipi di implementazione

Queste informazioni sono destinate agli utenti avanzati che dispongono di conoscenze approfondite sia nella generazione di rapporti che nell’implementazione. Non tentare di modificare l’implementazione senza comprenderne le conseguenze. Se hai bisogno di apportare modifiche all’implementazione, contatta l’Account Manager della tua organizzazione.

Se utilizzi più di un tipo di implementazione (ad esempio richieste JavaScript e di immagini codificate), assicurati che le seguenti variabili siano specificate e corrispondenti:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (se utilizzi SSL)

Se ciascuna di queste non corrisponde tra le diverse implementazioni, gli utenti possono essere tracciati come visitatori separati.
