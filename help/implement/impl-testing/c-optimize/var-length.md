---
description: La lunghezza delle variabili di Analytics può influire sulla dimensione dello snippet di codice HTML, sul file libreria javascript e sulla richiesta di immagini.
keywords: Implementazione di Analytics
seo-description: La lunghezza delle variabili di Analytics può influire sulla dimensione dello snippet di codice HTML, sul file libreria javascript e sulla richiesta di immagini.
seo-title: Lunghezza variabile
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Lunghezza variabile
topic: Sviluppatore e implementazione
uuid: 87 deabb 3-2 acb -4797-9 a 65-769 d 9 e 2 fbd 62
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Lunghezza variabile

La lunghezza delle variabili di Analytics può influire sulla dimensione dello snippet di codice HTML, sul file libreria javascript e sulla richiesta di immagini.

Se un cliente dispone di molte variabili (di lunghezza pari a 60 caratteri o più), i valori possono essere sostituiti con identificatori più brevi. Le classificazioni dei dati o le regole VISTA possono essere utilizzate per tradurre gli identificatori in nomi descrittivi.

>[!NOTE]
>
>La maggior parte delle variabili Analytics hanno un massimo di 100 caratteri (le evar hanno un massimo di 255). Internet Explorer consente un massimo di 2,048 caratteri in un URL della richiesta di immagine GET. Il limite di richiesta delle immagini non si applica solo alle variabili, ma anche alle informazioni relative al browser, al sistema operativo e ai plug-in del browser (solo Netscape/Mozilla).

