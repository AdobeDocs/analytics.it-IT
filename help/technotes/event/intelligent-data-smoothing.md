---
title: Uniformità intelligente dei dati
description: Scopri come l’uniformità intelligente dei dati analizza le tendenze della cronologia per prevedere il valore di qualsiasi metrica entro un periodo di tempo interessato.
feature: AI Tools
role: User, Admin
exl-id: b7a2e5d5-99d4-408d-84e6-67abff9e8727
source-git-commit: e0a4caec9bc58a0846cd46871aad3bed99d218a3
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 1%

---

# Uniformità intelligente dei dati

In rare occasioni, alcuni fattori possono influire sulla qualità dei dati. Il traffico dei bot, le modifiche di implementazione o le interruzioni del servizio possono influire sull’integrità dei dati raccolti. Complicano inoltre l’analisi di come l’evento possa aver influenzato la completezza dei dati.

L’uniformità intelligente dei dati è un prototipo in [Labs di Analytics](/help/analyze/labs.md) che può aiutare a completare questa visualizzazione analizzando le tendenze storiche per prevedere il valore di qualsiasi metrica entro il periodo di tempo interessato. Il prototipo applica algoritmi avanzati di apprendimento automatico per tracciare i valori previsti per le metriche nel periodo di tempo analizzato.

## Eseguire l’uniformità intelligente dei dati

1. Passa ad Adobe Analytics Labs:
   ![Labs](assets/labs.png)
1. Avvia il prototipo di uniformità intelligente dei dati.
   ![Avvia prototipo](assets/intelligent-ds.png)
1. Aggiungi la metrica da analizzare alla tabella a forma libera. Il prototipo funziona solo con granularità giornaliera, quindi assicurati che la dimensione nella tabella sia Giorno.
   ![Aggiungi metrica](assets/add-metric.png)
1. Scegli un intervallo di date più ampio della finestra dell’evento, ma assicurati che includa l’evento.
   ![Intervallo date](assets/date-range.png)
1. Fai clic sull’icona a forma di ingranaggio per la metrica nella tabella a forma libera.
   ![Icona ingranaggio](assets/gear-icon.png)
1. Sotto [!UICONTROL Data Settings], seleziona la [!UICONTROL Data smoothing] opzione.
   ![Uniformità dei dati](assets/column-setting.png)
1. Seleziona la data/intervallo di date corrispondente all’evento e fai clic su [!UICONTROL Apply].
Assicurati che l’intervallo di dati per l’uniformità dei dati sia un sottoinsieme dell’intervallo di date selezionato per il pannello. La metrica nella tabella e nel grafico viene sostituita dai valori previsti.
   ![Valori previsti](assets/predictive-values.png)
