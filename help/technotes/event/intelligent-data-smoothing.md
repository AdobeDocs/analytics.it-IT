---
title: Uniformità dei dati intelligente
description: Scopri in che modo l’ottimizzazione intelligente dei dati analizza le tendenze storiche per prevedere il valore di qualsiasi metrica in un periodo di tempo interessato.
feature: Strumenti di intelligenza artificiale
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: aa9f0a8f5b7b1780d0b0be729775c573e12caa35
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 1%

---

# Uniformità dei dati intelligente

In rare occasioni, alcuni fattori possono influire sulla qualità dei dati. Il traffico dei bot, le modifiche di implementazione o le interruzioni del servizio possono influire sull’integrità dei dati raccolti. Inoltre, complicano l’analisi su come l’evento possa aver influenzato la completezza dei dati.

Intelligent Data Smoothing è un prototipo in [Analytics Labs](/help/analyze/tech-previews/overview.md) che può aiutare a completare questa visualizzazione analizzando le tendenze della cronologia per prevedere il valore di qualsiasi metrica nel periodo di tempo interessato. Il prototipo applica algoritmi avanzati di apprendimento automatico per tracciare i valori previsti per le metriche nel periodo di tempo analizzato.

## Ottimizzazione intelligente dei dati

1. Passa a Adobe Analytics Labs:
   ![Labs](assets/labs.png)
1. Lanciare il prototipo Intelligent Data Smoothing.
   ![Prototipo di lancio](assets/intelligent-ds.png)
1. Aggiungi la metrica da analizzare alla tabella a forma libera. Il prototipo funziona solo con una granularità giornaliera, quindi accertati che la dimensione nella tabella sia Day (Giorno).
   ![Aggiungi metrica](assets/add-metric.png)
1. Scegli un intervallo di date più ampio della finestra dell’evento, ma accertati che includa l’evento.
   ![Intervallo date](assets/date-range.png)
1. Fai clic sull’icona a forma di ingranaggio per la metrica nella tabella a forma libera.
   ![Icona a forma di ingranaggio](assets/gear-icon.png)
1. In [!UICONTROL Data Settings], seleziona l’opzione [!UICONTROL Data smoothing].
   ![Uniformità dei dati](assets/column-setting.png)
1. Seleziona l’intervallo di date/date corrispondente all’evento e fai clic su [!UICONTROL Apply].
Assicurati che l’intervallo di dati per l’uniformità dei dati sia un sottoinsieme dell’intervallo di date selezionato per il pannello. La metrica nella tabella e nel grafico viene sostituita dai valori previsti.
   ![Valori previsti](assets/predictive-values.png)