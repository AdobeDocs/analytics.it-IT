---
title: Giorno del mese
description: Il giorno numerico del mese, indipendentemente dal mese.
feature: Dimensions
exl-id: 6d27aa9f-ce75-4a27-bb92-3acabe3975a1
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 4%

---

# Giorno del mese

La dimensione &quot;Giorno del mese&quot; indica il giorno numerico di un mese qualsiasi come elemento della dimensione. Ad esempio, se disponi di un rapporto che si estende dal 1° gennaio al 31 marzo, il primo di ogni mese viene raggruppato nello stesso elemento dimensionale. Questo rapporto è utile se desideri che un rapporto venga suddiviso per giorno, ma non vuoi che una data statica sia costituita da elementi dimensionali. È particolarmente utile come dimensione nei rapporti pianificati, in quanto questa dimensione viene rigenerata con l’intervallo di date selezionato.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Gli elementi di Dimension includono i numeri `1` - `31`, che rappresenta il giorno del mese in cui si è verificato l’hit.
