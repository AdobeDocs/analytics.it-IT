---
title: Giorno del mese
description: Il giorno numerico del mese, indipendentemente dal mese.
feature: Dimensions
exl-id: 6d27aa9f-ce75-4a27-bb92-3acabe3975a1
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---

# Giorno del mese

Il &#39;Giorno del mese&#39; [dimensione](overview.md) riporta il giorno numerico di un dato mese come elemento dimensione. Ad esempio, se un rapporto si estende dal 1° gennaio al 31 marzo, il primo di ogni mese si raggruppa nello stesso elemento dimensionale. Questo rapporto è utile se desideri un rapporto suddiviso per giorno, ma non vuoi una data statica come elementi dimensionali. È particolarmente utile come dimensione nei rapporti pianificati, in quanto questa dimensione viene aggregata all’intervallo di date selezionato.

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi del Dimension includono i numeri `1` - `31`, che rappresenta il giorno del mese in cui si è verificato l’hit.
