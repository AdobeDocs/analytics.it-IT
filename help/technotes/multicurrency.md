---
description: Descrive come definire i codici della valuta di destinazione per il funzionamento del supporto multi-valuta.
title: Supporto multi-valuta
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
TQID: https://experienceleague.adobe.com/-t0JAIvbmUmzTCTznOWcjVmvtJbmQNV5MIrbQBvhv6M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 127
ht-degree: 4%

---

# Supporto multi-valuta

Adobe offre diversi livelli di conversione della valuta, in modo che la tua organizzazione possa ottenere la valuta desiderata in molti rapporti. La conversione avviene a tre livelli:

## Livello pagina

È possibile utilizzare la variabile [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) per impostare la valuta desiderata in ogni pagina. Se la valuta sulla pagina non corrisponde a quella della suite di rapporti di destinazione, Adobe esegue una conversione della valuta nella valuta della suite di rapporti in base al tasso di cambio del giorno corrente. Viene registrata la valuta convertita.

## Livello suite di rapporti

Ogni suite di rapporti ha una **valuta di base**. Questa valuta determina il contesto di tutte le metriche di valuta (ad esempio [Entrate](/help/components/metrics/revenue.md)). Tutti i dati di valuta memorizzati sono nella valuta di base della suite di rapporti.

