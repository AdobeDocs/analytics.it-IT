---
description: Un "livello dati" è un framework di oggetti JavaScript che gli sviluppatori inseriscono nelle pagine.
keywords: Analytics Implementation;data layer;digitalData
seo-description: Un "livello dati" è un framework di oggetti JavaScript che gli sviluppatori inseriscono nelle pagine. I livelli di dati possono essere utilizzati dagli strumenti di tracciamento (compresi i sistemi di gestione tag come Gestione tag dinamica) per compilare i rapporti.
seo-title: Livello dati
solution: Analytics
title: Livello dati
topic: Sviluppatore e implementazione
uuid: dedb2a50-06f3-4354-8993-a25d4952ce1e
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Livello dati

Un livello __ dati è un framework di oggetti JavaScript che gli sviluppatori inseriscono nelle pagine. I livelli di dati possono essere utilizzati dagli strumenti di tracciamento (inclusi i sistemi di gestione tag come Adobe Experience Platform Launch e Gestione tag dinamica) per compilare i rapporti.

L'implementazione di un livello dati sul sito offre un controllo e una flessibilità superiori rispetto all'implementazione e consente di effettuare la manutenzione più semplice &#x200B; fasi future. I nomi di questi oggetti JavaScript sono teoricamente arbitrari, ma la procedura ottimale consiste nell'utilizzare elementi coerenti e prevedibili. Gli sviluppatori potrebbero già avere un livello dati o una preferenza per il formato. Ci sono pochi standard diversi che la comunità di monitoraggio ha creato come punto di partenza. Il documento sulle specifiche di implementazione [del livello](assets/datalayer-documentation.pdf) dati per Analytics utilizza l'oggetto "digitalData" standard W3C accettato dalla più ampia varietà di tecnologie di tracciamento, nel caso in cui sia necessario utilizzare il livello dati per più di questa implementazione di Gestione dinamica dei tag.
