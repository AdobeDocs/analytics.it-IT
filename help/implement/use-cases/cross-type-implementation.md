---
title: Tracciare diversi tipi di implementazione
description: Utilizza diversi tipi di implementazione e monitora i visitatori in modo diretto tra di loro.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Tracciare diversi tipi di implementazione

Queste informazioni sono destinate agli utenti avanzati che hanno esperienza sia nel reporting che nell&#39;implementazione. Non tentare di modificare l&#39;implementazione senza comprenderne le conseguenze. Se hai bisogno di modifiche all&#39;implementazione, contatta l&#39;Account Manager della tua organizzazione.

Se utilizzate più di un tipo di implementazione (ad esempio, richieste JavaScript e di immagini hardcoded), accertatevi che le seguenti variabili siano specificate e corrispondano tra loro:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`*(se si utilizza SSL)

Se ognuna di queste non corrisponde tra le diverse implementazioni, gli utenti possono essere tracciati come visitatori separati.
