---
description: La lunghezza delle variabili Analytics può influenzare le dimensioni dello snippet di codice HTML, del file libreria JavaScript e della richiesta di immagini.
keywords: Implementazione di Analytics
seo-description: La lunghezza delle variabili Analytics può influenzare le dimensioni dello snippet di codice HTML, del file libreria JavaScript e della richiesta di immagini.
seo-title: Lunghezza della variabile
solution: Analytics
subtopic: Risoluzione dei problemi
title: Lunghezza della variabile
topic: Sviluppatore e implementazione
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Lunghezza della variabile

La lunghezza delle variabili Analytics può influenzare le dimensioni dello snippet di codice HTML, del file libreria JavaScript e della richiesta di immagini.

Se un cliente ha molte variabili lunghe (almeno 60 caratteri), i valori possono essere sostituiti con identificatori più brevi. Le classificazioni dei dati o le regole VISTA possono essere utilizzate per tradurre gli identificatori in nomi descrittivi.

> [!NOTE] La maggior parte delle variabili Analytics contiene un massimo di 100 caratteri (le eVar hanno un massimo di 255). Internet Explorer consente un massimo complessivo di 2.048 caratteri in un URL di richiesta immagine GET. Il limite di richieste di immagini si applica non solo alle variabili, ma anche alle informazioni sul browser, il sistema operativo e i plug-in del browser (solo Netscape/Mozilla).

