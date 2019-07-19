---
description: Queste informazioni sono destinate agli utenti avanzati che sono ben orientati sia ai reporting che all'implementazione. Non tentare di modificare l'implementazione senza comprendere le conseguenze. Se avete bisogno di modifiche di implementazione, contattate l'Account Manager della vostra organizzazione.
keywords: Implementazione di Analytics
seo-description: Queste informazioni sono destinate agli utenti avanzati che sono ben orientati sia ai reporting che all'implementazione. Non tentare di modificare l'implementazione senza comprendere le conseguenze. Se avete bisogno di modifiche di implementazione, contattate l'Account Manager della vostra organizzazione.
seo-title: Tracciare diversi tipi di implementazione
solution: Analytics
title: Tracciare diversi tipi di implementazione
topic: Sviluppatore e implementazione
uuid: a 0 a 3229 a -79 a 2-4 dc 2-b 0 be -4 b 8 fac 2 efa 3 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Tracciare diversi tipi di implementazione

Queste informazioni sono destinate agli utenti avanzati che sono ben orientati sia ai reporting che all'implementazione. Non tentare di modificare l'implementazione senza comprendere le conseguenze. Se avete bisogno di modifiche di implementazione, contattate l'Account Manager della vostra organizzazione.

Se utilizzi più di un tipo di implementazione (ad esempio, javascript e richieste di immagini hardcoded), assicurati che le seguenti variabili siano specificate e che corrispondano a vicenda:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (se utilizzate SSL)

Se ciascuna di queste non corrisponde a diverse implementazioni, gli utenti possono essere tracciati come visitatori separati.
