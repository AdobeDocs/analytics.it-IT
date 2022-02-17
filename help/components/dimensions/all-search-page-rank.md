---
title: Classificazione di tutte le pagine di ricerca
description: Determina la pagina su un motore di ricerca su cui un visitatore ha fatto clic per accedere al sito.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 5%

---

# Classificazione di tutte le pagine di ricerca

La dimensione &quot;All search page rank&quot; fornisce informazioni sulla pagina dei risultati di ricerca che un visitatore ha fatto clic sul sito. Ad esempio, se il sito viene visualizzato nella seconda pagina dei risultati di ricerca di un motore di ricerca, l’elemento dimensione per questa variabile è &quot;Pagina di ricerca 2&quot;.

## Popolare questa dimensione con i dati

Per far funzionare questa dimensione è sufficiente che la suite di rapporti disponga di [Filtri URL interni](/help/admin/admin/internal-url-filter-admin.md) configurato correttamente. AppMeasurement compila automaticamente questa dimensione senza alcuna modifica del codice di implementazione.

## Elementi Dimension

Se un visitatore fa clic sul sito da un motore di ricerca, il valore di questa dimensione è &quot;Pagina di ricerca&quot; seguito dal numero di pagina su cui ha fatto clic. Se un hit non proviene da un motore di ricerca, il valore di questa dimensione è &quot;Non specificato&quot;.
