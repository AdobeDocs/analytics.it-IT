---
description: Un "livello dati" è un framework di oggetti javascript che gli sviluppatori inseriscono nelle pagine.
keywords: Implementazione di Analytics; livello dati; Digitaldata
seo-description: Un "livello dati" è un framework di oggetti javascript che gli sviluppatori inseriscono nelle pagine. I livelli dati possono essere utilizzati mediante gli strumenti di tracciamento (inclusi i sistemi di gestione tag come Gestione tag dinamica) per compilare i rapporti.
seo-title: Livello dati
solution: Analytics
title: Livello dati
topic: Sviluppatore e implementazione
uuid: dedb 2 a 50-06 f 3-4354-8993-a 25 d 4952 ce 1 e
translation-type: tm+mt
source-git-commit: 26c3cc9895c27d6abc452e0a4636771fb2415fb3

---


# Livello dati

A _data layer_ is a framework of JavaScript objects that developers insert into pages. I livelli dati possono essere utilizzati dagli strumenti di tracciamento (inclusi i sistemi di gestione tag come Adobe Experience Platform Launch e Gestione tag dinamica) per compilare i rapporti.

L'implementazione di un livello dati sul sito fornisce un controllo e una flessibilità ottimali per la tua implementazione e consente la manutenzione più semplice in fase futura. I nomi di questi oggetti javascript sono teoricamente arbitrari, ma si consiglia di utilizzare qualcosa di coerente e prevedibile. Gli sviluppatori possono già disporre di un livello di dati o di una preferenza per il formato. La community di tracciamento è stata creata come punto di partenza. The [Data Layer for Analytics Implementation](assets/datalayer-documentation.pdf) specification document uses the W3C standard "digitalData" object that is accepted by the widest variety of tracking technology, in case there is a need to use the data layer for more than this DTM implementation.
