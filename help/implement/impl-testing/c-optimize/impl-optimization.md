---
description: La distribuzione di Analytics è organizzata in tre fasi principali.
keywords: Implementazione di Analytics
seo-description: La distribuzione di Analytics è organizzata in tre fasi principali.
seo-title: Panoramica sull'ottimizzazione
solution: Analytics
subtopic: Risoluzione dei problemi
title: Panoramica sull'ottimizzazione
topic: Sviluppatore e implementazione
uuid: 8e8ecc5b-d4b1-4d13-8525-39e4924df247
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Panoramica sull'ottimizzazione

La distribuzione di Analytics è organizzata in tre fasi principali.

1. Ciò comporta l’incollaggio di uno snippet di codice HTML su ciascuna pagina (o modello di pagina) di un sito Web. Lo snippet di codice HTML è molto piccolo (da 400 a 1.000 byte) e contiene variabili JavaScript e altri identificatori che semplificano il processo di raccolta dei dati.
1. Lo snippet di codice chiama un file libreria JavaScript che contiene funzioni JavaScript specifiche per Analytics utilizzate durante la raccolta delle metriche. Se il codice di Analytics è implementato correttamente, il tempo richiesto dal browser per eseguire il file libreria JavaScript è in genere trascurabile.

1. Il file libreria invia una richiesta di immagine a un server di raccolta dati Adobe. Il server raccoglie i dati inviati e restituisce un'immagine trasparente 1x1 al browser del visitatore. Questo terzo passaggio aggiunge un incremento significativo al tempo di download totale delle pagine.

> [!NOTE] I clienti possono adottare ulteriori misure per ridurre il sovraccarico di Analytics.

