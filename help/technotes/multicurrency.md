---
description: Descrive come definire i codici della valuta di destinazione per il funzionamento del supporto multi-valuta.
title: Supporto multi-valuta
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 2%

---

# Supporto multi-valuta

Adobe offre più livelli di conversione della valuta in modo che l’organizzazione possa ottenere la valuta desiderata in molti rapporti. La conversione avviene a tre livelli:

## Livello pagina

È possibile utilizzare [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) per impostare la valuta desiderata su ogni pagina. Se la valuta sulla pagina non corrisponde a quella della suite di rapporti di destinazione, Adobe esegue una conversione della valuta nella valuta della suite di rapporti in base al tasso di cambio del giorno corrente. Viene registrata la valuta convertita.

## Livello suite di rapporti

Ogni suite di rapporti ha una **valuta di base**. Questa valuta determina il contesto di tutte le metriche di valuta (come [Ricavi](/help/components/metrics/revenue.md)). Tutti i dati di valuta memorizzati sono nella valuta di base della suite di rapporti.

## Livello utente

Per Reports &amp; Analytics, gli utenti possono impostare una valuta diversa dalla valuta di base della suite di rapporti in [Impostazioni dei rapporti](/help/analyze/reports-analytics/report-settings.md). Questa impostazione non è distruttiva, ovvero non altera i dati sottostanti. Applica invece la conversione della valuta di base a tutti i rapporti visualizzati in base al tasso di cambio odierno. Se lo stesso rapporto viene visualizzato in giorni diversi, i numeri possono cambiare a causa di tassi di cambio giornalieri diversi.

Analysis Workspace attualmente non offre la conversione della valuta a livello di utente.
