---
description: Nome del collegamento su cui è stato fatto clic.
title: Collegamento Activity Map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 4%

---

# Collegamento Activity Map

In &#39;Collegamento Activity Map&#39; [dimensione](overview.md) sono visualizzati i collegamenti più popolari su cui è stato fatto clic. Puoi utilizzare questa dimensione per confrontare quali collegamenti sul tuo sito sono più utilizzati, indipendentemente da dove sono stati cliccati.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla [variabile di dati di contesto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`. Se l&#39;implementazione utilizza [Activity Map](/help/analyze/activity-map/overview.md), questa variabile di dati di contesto raccoglie automaticamente i dati quando si fa clic sui collegamenti.

Per un determinato collegamento su cui hai fatto clic, Activity Map cerca i seguenti elementi (in ordine):

1. La variabile `s_objectID`
1. Testo interno del collegamento
1. Attributo `alt` per le immagini
1. Attributo `title`
1. Attributo `src` per le immagini
1. Attributo `action` per i moduli

Se l’elemento su cui è stato fatto clic non contiene nessuno dei criteri di cui sopra, Activity Map non raccoglie i dati per tale clic.

## Elementi dimensionali

Gli elementi di Dimension includono il testo del collegamento o altri attributi di collegamento su cui i visitatori fanno clic. La struttura e l’implementazione del sito della tua organizzazione determinano i valori esatti raccolti.
