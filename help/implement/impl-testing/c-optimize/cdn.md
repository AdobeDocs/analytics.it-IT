---
description: I servizi di distribuzione dei contenuti o le reti CDN (Content Distribution Networks) come Akamai e Speedera inviano i contenuti Web in modo più vicino al bordo della rete, mantenendo i documenti richiesti di frequente in prossimità della posizione in cui sono accessibili.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Servizi di distribuzione del contenuto/delle reti
topic: Developer and implementation
uuid: 6cb57c59-d0f9-4ca5-9f15-0e74e585a4a1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Servizi di distribuzione del contenuto/delle reti

I servizi di distribuzione dei contenuti o le reti CDN (Content Distribution Networks) come Akamai e Speedera inviano i contenuti Web in modo più vicino al bordo della rete, mantenendo i documenti richiesti di frequente in prossimità della posizione in cui sono accessibili.

In genere, questo riduce la latenza di accesso, l'utilizzo della larghezza di banda e i costi dell'infrastruttura.

Il file AppMeasurement per la libreria JavaScript può essere distribuito tramite un CDN per migliorare le prestazioni e la consegna del file al visitatore del sito. I clienti Adobe devono accertarsi di aver configurato correttamente i propri servizi CDN. I CDN sono un motivo comune per fluttuare nei tempi di download e dovrebbero essere considerati la causa più probabile di eventuali modifiche nei tempi di download.

Gestione tag memorizza tutti i JavaScript in una CDN.
