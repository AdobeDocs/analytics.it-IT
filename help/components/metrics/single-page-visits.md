---
title: Visite a pagina singola (metriche)
description: Il numero di volte in cui l’elemento dimensione "Pagina" non è cambiato in una visita.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 11%

---

# Visite a pagina singola

*Questa pagina della guida descrive il funzionamento di &quot;Visite a pagina singola&quot; come metrica. Per ulteriori informazioni, consulta la dimensione [Visite a pagina singola](../dimensions/single-page-visits.md).*

La [!UICONTROL Single page visits] [metrica](overview.md) mostra il numero di visite in cui l&#39;elemento dimensione [Pagina](../dimensions/page.md) conteneva un solo valore univoco per l&#39;intera visita. Questa metrica è utile nel contesto di dimensioni in cui desideri visualizzare visite brevi, ma non ha la stessa severità di una regola di [[!UICONTROL Bounces]](bounces.md).

## Come è calcolata questa metrica

Questa metrica conta il numero di visite in cui l&#39;elemento dimensione [!UICONTROL Page] conteneva un solo valore univoco per l&#39;intera visita. Se un visitatore ricarica la pagina o genera chiamate di tracciamento dei collegamenti, conta ancora come una visita a pagina singola. Non appena la dimensione Pagina diventa un secondo valore univoco, la visita non si qualifica più come visita a pagina singola.

Vedi [Accesso singolo](single-access.md) per un confronto tra metriche.

## Conta istanze ripetute

Questa impostazione consente di specificare se le istanze ripetute vengono conteggiate nei rapporti. Per ulteriori informazioni, vedere [Conteggio istanze ripetute](/help/components/metrics/count-repeat-instances.md).
