---
title: Gerarchia
description: (Ritirato) Una dimensione personalizzata che puoi utilizzare nei rapporti.
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 86%

---

# Gerarchia

>[!IMPORTANT]
>
>Questa dimensione è stata ritirata e non è una [dimensione](overview.md) disponibile in Analysis Workspace. Al suo posto, Adobe consiglia di utilizzare le [eVar](evar.md) e le classificazioni.

Le gerarchie sono variabili personalizzate che puoi utilizzare come preferisci. Non persistono oltre l’hit impostato. Se il contratto con Adobe lo supporta, sono disponibili fino a 5 gerarchie.

## Popolare le gerarchie con i dati

Ogni gerarchia raccoglie dati dalla stringa di query [`h1` - `h5` ](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il parametro della stringa di query `h1` raccoglie i dati per la gerarchia 1, mentre il parametro della stringa di query `h4` raccoglie i dati per la gerarchia 4.

AppMeasurement, che compila variabili JavaScript in una richiesta di immagine per la raccolta dati, utilizza le variabili `hier1` - `hier5`. Per le linee guida per l’implementazione, consulta [qui](/help/implement/vars/page-vars/hier.md) nella Guida utente di implementazione.

## Elementi dimensionali

Poiché le gerarchie contengono stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali di ciascuna gerarchia. Assicurati di registrare lo scopo di ogni gerarchia e degli elementi dimensionali tipici in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).
