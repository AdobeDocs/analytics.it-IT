---
title: Classificazione di tutte le pagine di ricerca
description: Determina quale pagina di un motore di ricerca un visitatore ha fatto clic sul tuo sito.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 10%

---

# Classificazione di tutte le pagine di ricerca

La [dimensione](overview.md) di &quot;Classificazione di tutte le pagine di ricerca&quot; fornisce informazioni approfondite sulla pagina dei risultati della ricerca in cui un visitatore ha fatto clic sul sito. Ad esempio, se il sito viene visualizzato nella seconda pagina dei risultati di ricerca di un motore di ricerca, l’elemento dimensionale per questa variabile è &quot;Pagina di ricerca 2&quot;.

## Popolare questa dimensione con i dati

Per far funzionare questa dimensione è necessario che la suite di rapporti disponga di [Filtri per URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) configurati correttamente. AppMeasurement compila automaticamente questa dimensione senza alcuna modifica del codice di implementazione.

## Elementi dimensionali

Se un visitatore fa clic sul tuo sito da un motore di ricerca, il valore di questa dimensione è &quot;Pagina di ricerca&quot; seguito dal numero di pagina in cui ha fatto clic. Se un hit non proviene da un motore di ricerca, il valore di questa dimensione è &quot;Non specificato&quot;.
