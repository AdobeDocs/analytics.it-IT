---
title: Dimensioni di uscita
description: Elenca le dimensioni di uscita e il relativo utilizzo.
keywords: chiudi pagina, esci dalla sezione del sito, esci dal server, esci da approfondimenti personalizzati
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%

---

# Dimensioni di uscita

*Questa pagina della Guida descrive il funzionamento delle uscite come [dimensione](overview.md). Per informazioni sul funzionamento delle uscite come metrica, vedi la metrica [Uscite](../metrics/exits.md).*

Le dimensioni di uscita registrano l’ultimo elemento dimensione e lo applicano retroattivamente a tutti gli hit nella visita. Le dimensioni di uscita sono disponibili per tutte le variabili con percorsi abilitati in [Variabili di traffico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti.

## Popolare le dimensioni di uscita con i dati

Una determinata dimensione di uscita è basata sulla variabile di traffico associata. Se la variabile non-exit contiene dati, anche la dimensione di uscita associata contiene dati. Se le variabili di traffico contengono dati, per le dimensioni di uscita non sono necessarie modifiche di implementazione.

## Elementi dimensionali

Poiché le variabili di uscita sono in genere basate su stringhe personalizzate nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. I valori in una determinata dimensione di uscita corrispondono agli elementi dimensionali nella dimensione non di uscita associata. Ad esempio, gli elementi dimensionali nella dimensione &quot;Pagina di uscita&quot; contengono elementi dimensionali simili nella dimensione &quot;Pagina&quot;.
