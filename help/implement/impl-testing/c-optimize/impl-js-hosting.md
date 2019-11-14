---
description: L'inserimento della chiamata al file di libreria JavaScript nella parte superiore della pagina fa sì che l'immagine sia uno dei primi elementi da scaricare.
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: Posizione file JavaScript e relativa contemporaneità
topic: Developer and implementation
uuid: ed5118a8-b142-4fab-8aa1-92d931cc1439
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Posizione file JavaScript e relativa contemporaneità

L'inserimento della chiamata al file di libreria JavaScript nella parte superiore della pagina fa sì che l'immagine sia uno dei primi elementi da scaricare.

La maggior parte dei browser Web scarica le immagini contemporaneamente. In genere, è possibile scaricare simultaneamente da tre a quattro immagini.

Poiché la maggior parte dei browser Web scarica gli elementi contemporaneamente, la barra di stato di molti browser comuni (incluso Internet Explorer) non riflette con precisione quale elemento il browser sta tentando di caricare. Ad esempio, la barra di stato potrebbe indicare che il browser è in attesa del download dell’immagine 1. I test dei pacchetti di rete mostrano che il browser ha già ricevuto l'immagine 1 e che è in attesa dell'immagine 2.

> [!NOTE] Poiché i fornitori di servizi di audit delle prestazioni Internet di terze parti (ad esempio, Keynote Systems) scaricano in sequenza gli elementi immagine della pagina, non simultaneamente, non imitano la tipica esperienza utente.

