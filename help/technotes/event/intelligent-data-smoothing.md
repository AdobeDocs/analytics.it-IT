---
title: Uniformità intelligente dei dati
description: Scopri come l’uniformità intelligente dei dati analizza le tendenze della cronologia per prevedere il valore di qualsiasi metrica entro un periodo di tempo interessato.
feature: AI Tools
role: User, Admin
exl-id: b7a2e5d5-99d4-408d-84e6-67abff9e8727
TQID: 'https://experienceleague.adobe.com/iqjuEBGaCRcwmWfZo6rC1DXi8y4iyj9gB87tpvXmJdk'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: b7156124-d291-4de4-ac0c-ed17d8078449
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 50f9ff18816ad88f231762b8b37c1ab9e1787b6f
workflow-type: tm+mt
source-wordcount: 251
ht-degree: 1%

---

# Uniformità intelligente dei dati

In rare occasioni, alcuni fattori possono influire sulla qualità dei dati. Il traffico dei bot, le modifiche di implementazione o le interruzioni del servizio possono influire sull’integrità dei dati raccolti. Complicano inoltre l’analisi di come l’evento possa aver influenzato la completezza dei dati.

L&#39;uniformità intelligente dei dati è un prototipo in [Analytics Labs](/help/analyze/labs.md) che può aiutare a completare questa visualizzazione analizzando le tendenze della cronologia per prevedere il valore di qualsiasi metrica entro il periodo di tempo interessato. Il prototipo applica algoritmi avanzati di apprendimento automatico per tracciare i valori previsti per le metriche nel periodo di tempo analizzato.

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
1. In [!UICONTROL Data Settings], selezionare l&#39;opzione [!UICONTROL Data smoothing].
   ![Uniformità dati](assets/column-setting.png)
1. Selezionare la data/intervallo di date corrispondente all&#39;evento e fare clic su [!UICONTROL Apply].
Assicurati che l’intervallo di dati per l’uniformità dei dati sia un sottoinsieme dell’intervallo di date selezionato per il pannello. La metrica nella tabella e nel grafico viene sostituita dai valori previsti.
   ![Valori previsti](assets/predictive-values.png)
