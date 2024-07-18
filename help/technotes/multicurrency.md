---
description: Descrive come definire i codici della valuta di destinazione per il funzionamento del supporto multi-valuta.
title: Supporto multi-valuta
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: 99156dd9d898ce0abf214561cb0040c647d7e6ab
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 3%

---

# Supporto multi-valuta

Adobe offre più livelli di conversione della valuta in modo che l’organizzazione possa ottenere la valuta desiderata in molti rapporti. La conversione avviene a tre livelli:

## Livello pagina

È possibile utilizzare la variabile [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) per impostare la valuta desiderata in ogni pagina. Se la valuta sulla pagina non corrisponde a quella della suite di rapporti di destinazione, Adobe esegue una conversione della valuta nella valuta della suite di rapporti in base al tasso di cambio del giorno corrente. Viene registrata la valuta convertita.

## Livello suite di rapporti

Ogni suite di rapporti ha una **valuta di base**. Questa valuta determina il contesto di tutte le metriche di valuta (ad esempio [Entrate](/help/components/metrics/revenue.md)). Tutti i dati di valuta memorizzati sono nella valuta di base della suite di rapporti.

