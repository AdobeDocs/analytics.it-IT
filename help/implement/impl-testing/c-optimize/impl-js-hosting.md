---
description: L'inserimento della chiamata al file di libreria JavaScript nella parte superiore della pagina fa sì che l'immagine sia uno dei primi elementi da scaricare.
keywords: Implementazione di Analytics
seo-description: L'inserimento della chiamata al file di libreria JavaScript nella parte superiore della pagina fa sì che l'immagine sia uno dei primi elementi da scaricare.
seo-title: Posizione file JavaScript e relativa contemporaneità
solution: Analytics
subtopic: Risoluzione dei problemi
title: Posizione file JavaScript e relativa contemporaneità
topic: Sviluppatore e implementazione
uuid: ed5118a8-b142-4fab-8aa1-92d931cc1439
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Posizione file JavaScript e relativa contemporaneità

L'inserimento della chiamata al file di libreria JavaScript nella parte superiore della pagina fa sì che l'immagine sia uno dei primi elementi da scaricare.

La maggior parte dei browser Web scarica le immagini contemporaneamente. In genere, è possibile scaricare simultaneamente da tre a quattro immagini.

Poiché la maggior parte dei browser Web scarica gli elementi contemporaneamente, la barra di stato di molti browser comuni (incluso Internet Explorer) non riflette con precisione quale elemento il browser sta tentando di caricare. Ad esempio, la barra di stato potrebbe indicare che il browser è in attesa del download dell’immagine 1. I test dei pacchetti di rete mostrano che il browser ha già ricevuto l'immagine 1 e che è in attesa dell'immagine 2.

> [!NOTE] Poiché i fornitori di servizi di audit delle prestazioni Internet di terze parti (ad esempio, Keynote Systems) scaricano in sequenza gli elementi immagine della pagina, non simultaneamente, non imitano la tipica esperienza utente.

