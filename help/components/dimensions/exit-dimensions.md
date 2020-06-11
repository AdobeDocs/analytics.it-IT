---
title: Dimensioni di uscita
description: Elenca le dimensioni di uscita e il loro utilizzo.
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# Dimensioni di uscita

*In questa pagina della guida viene descritto come le uscite funzionano come una dimensione. Per informazioni sul funzionamento delle uscite come una metrica, vedi la metrica[Exits](../metrics/exits.md).*

Le dimensioni di uscita registrano l’ultimo valore di dimensione e lo applicano retroattivamente a tutti gli hit della visita. Le dimensioni di uscita sono disponibili per tutte le variabili con percorso abilitato nelle variabili [](/help/admin/admin/c-traffic-variables/traffic-var.md) Traffico nelle impostazioni della suite di rapporti.

## Compilare le dimensioni di uscita con i dati

Una determinata dimensione di uscita è basata sulla variabile di traffico associata. Se la variabile non uscita contiene dati, la relativa dimensione di uscita associata contiene anche dati. Non sono necessarie modifiche di implementazione per le dimensioni di uscita se le variabili di traffico contengono dati.

## Valori dimensione

Poiché le variabili exit sono in genere basate su stringhe personalizzate nell’implementazione, l’organizzazione determina i valori di dimensione. I valori in una data dimensione di uscita corrispondono ai valori di dimensione nella dimensione associata non di uscita. Ad esempio, i valori di dimensione nella dimensione &quot;Pagina di uscita&quot; contengono valori di dimensione simili nella dimensione &quot;Pagina&quot;.
