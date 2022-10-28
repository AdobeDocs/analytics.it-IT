---
title: Gerarchia
description: Una dimensione personalizzata che puoi utilizzare nel reporting.
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 1%

---

# Gerarchia

>[!IMPORTANT]
>
>Questa dimensione è ritirata e non è disponibile in Analysis Workspace. Adobe consiglia di utilizzare [eVar](evar.md) e classificazioni.

Le gerarchie sono variabili personalizzate che puoi utilizzare come desideri. Non persistono oltre il risultato impostato. Sono disponibili fino a 5 gerarchie se il contratto con Adobe lo supporta.

## Compilare gerarchie con i dati

Ogni gerarchia raccoglie dati dal [`h1` - `h5` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il `h1` il parametro della stringa di query raccoglie i dati per la gerarchia 1, mentre il `h4` il parametro della stringa query raccoglie i dati per la gerarchia 4.

AppMeasurement, che compila variabili JavaScript in una richiesta di immagine per la raccolta dei dati, utilizza le variabili `hier1` - `hier5`. Vedi [hier](/help/implement/vars/page-vars/hier.md) nella guida utente Implementa per le linee guida di implementazione.

## Elementi Dimension

Poiché le gerarchie contengono stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali di ciascuna gerarchia. Assicurati di registrare lo scopo di ogni gerarchia e degli elementi dimensionali tipici in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).
