---
description: La distribuzione di Analytics è organizzata in tre passaggi principali.
keywords: Implementazione di Analytics
seo-description: La distribuzione di Analytics è organizzata in tre passaggi principali.
seo-title: Panoramica sull'ottimizzazione
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Panoramica sull'ottimizzazione
topic: Sviluppatore e implementazione
uuid: 8 e 8 ecc 5 b-d 4 b 1-4 d 13-8525-39 e 4924 df 247
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Panoramica sull'ottimizzazione

La distribuzione di Analytics è organizzata in tre passaggi principali.

1. Questo richiede di incollare uno snippet di codice HTML su ogni pagina (o modello pagina) di un sito Web. Lo snippet di codice HTML è molto piccolo (da 400 a 1,000 byte) e contiene variabili javascript e altri identificatori che agevolano il processo di raccolta dei dati.
1. Lo snippet di codice chiama un file libreria javascript contenente funzioni javascript specifiche di Analytics utilizzate durante la raccolta delle metriche. Se il codice di Analytics è implementato correttamente, il tempo necessario al browser per eseguire il file di libreria javascript è generalmente trascurabile.

1. Il file libreria invia una richiesta di immagine a un server di raccolta dati Adobe. Il server raccoglie i dati in corso di invio e restituisce un'immagine trasparente da 1 x 1 al browser del visitatore. Questo terzo passaggio aggiunge un incremento irrilevante al tempo totale di download della pagina.

>[!NOTE]
>
>I clienti possono effettuare ulteriori passaggi per ridurre il sovraccarico di Analytics.

