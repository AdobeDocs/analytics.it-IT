---
title: Dimensioni di uscita
description: Elenca le dimensioni di uscita e il loro utilizzo.
keywords: uscire dalla pagina, uscire dalla sezione del sito, uscire dal server, uscire da informazioni personalizzate
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# Dimensioni di uscita

*Questa pagina di aiuto descrive come le uscite funzionano come una dimensione. Per informazioni sul funzionamento delle uscite come metrica, consulta la [Uscite](../metrics/exits.md) metrica.*

Le dimensioni di uscita registrano l’ultimo elemento dimensione e lo applicano retroattivamente a tutti gli hit della visita. Le dimensioni di uscita sono disponibili per tutte le variabili con il percorso abilitato in [Variabili del traffico](/help/admin/admin/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti.

## Popolare le dimensioni di uscita con i dati

Una determinata dimensione di uscita è basata sulla variabile di traffico associata. Se la variabile non di uscita contiene dati, anche la dimensione di uscita associata contiene dati. Non sono necessarie modifiche di implementazione per le dimensioni di uscita se le variabili di traffico contengono dati.

## Elementi Dimension

Poiché le variabili exit sono in genere basate su stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali desiderati. I valori in una data dimensione di uscita corrispondono agli elementi dimensionali nella dimensione non di uscita associata. Ad esempio, gli elementi dimensionali nella dimensione &quot;Pagina di uscita&quot; contengono elementi dimensionali simili nella dimensione &quot;Pagina&quot;.
