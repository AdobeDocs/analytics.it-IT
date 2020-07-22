---
title: Tutti i livelli delle pagine di ricerca
description: Determinate la pagina in un motore di ricerca su cui un visitatore ha fatto clic per passare al sito.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# Tutti i livelli delle pagine di ricerca

La dimensione &#39;All search page rank&#39; (Tutto il livello di pagina di ricerca) fornisce informazioni sulla pagina dei risultati della ricerca che un visitatore ha fatto clic sul sito. Ad esempio, se il sito viene visualizzato nella seconda pagina dei risultati di ricerca di un motore di ricerca, l’elemento dimensione per questa variabile è &quot;Pagina di ricerca 2&quot;.

## Compilare questa dimensione con i dati

Per far funzionare questa dimensione è necessario che nella suite di rapporti siano impostati correttamente i filtri [URL](/help/admin/admin/internal-url-filter-admin.md) interni. AppMeasurement compila automaticamente questa dimensione senza alcuna modifica del codice di implementazione.

## Elementi dimensione

Se un visitatore fa clic sul sito da un motore di ricerca, il valore di questa dimensione è &quot;Pagina di ricerca&quot; seguito dal numero di pagina su cui ha fatto clic. Se un hit non proviene da un motore di ricerca, il valore di questa dimensione è &quot;Non specificato&quot;.
