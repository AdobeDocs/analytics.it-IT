---
description: Descrive come definire codici valuta di destinazione per il funzionamento del supporto multi-valuta.
title: Supporto multi-valuta
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 2%

---

# Supporto multi-valuta

In Adobe sono disponibili diversi livelli di conversione della valuta per consentire all’organizzazione di ottenere la valuta desiderata in molti rapporti. La conversione avviene a tre livelli:

## Livello pagina

È possibile utilizzare [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) per impostare la valuta desiderata su ogni pagina. Se la valuta nella pagina non corrisponde alla valuta della suite di rapporti di destinazione, Adobe esegue una conversione di valuta nella valuta della suite di rapporti in base al tasso di cambio del giorno corrente. La valuta convertita viene registrata.

## Livello suite di rapporti

Ogni suite di rapporti ha **valuta di base**. Questa valuta determina il contesto di tutte le metriche della valuta (ad esempio [Entrate](/help/components/metrics/revenue.md)). Tutti i dati di valuta memorizzati si trovano nella valuta di base della suite di rapporti.

## Livello utente

Per Reports &amp; Analytics, gli utenti possono impostare una valuta diversa dalla valuta di base della suite di rapporti in [Impostazioni dei rapporti](/help/analyze/reports-analytics/report-settings.md). Questa impostazione non è distruttiva, il che significa che non altera i dati sottostanti. Applica invece la conversione della valuta di base a tutti i rapporti visualizzati in base al tasso di cambio attuale. Se lo stesso rapporto viene visualizzato in giorni diversi, i numeri possono variare a causa dei diversi tassi di cambio giornalieri.

Al momento, Analysis Workspace non offre conversioni valutarie a livello di utente.
