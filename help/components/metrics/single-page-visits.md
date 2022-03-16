---
title: Visite a pagina singola (metriche)
description: Il numero di volte in cui l’elemento della dimensione "Pagina" non è stato modificato in una visita.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 8%

---

# Visite a pagina singola

*Questa pagina di aiuto descrive il funzionamento di &quot;visite a pagina singola&quot; come metrica. Consulta la sezione [Visite a pagina singola](../dimensions/single-page-visits.md) per ulteriori informazioni.*

La [!UICONTROL Single page visits] mostra il numero di visite in cui il [Pagina](../dimensions/page.md) l’elemento dimensionale conteneva un solo valore univoco per l’intera visita. Questa metrica è utile nel contesto delle dimensioni in cui desideri visualizzare visite brevi, ma non ha lo stesso livello di rigore di una regola [[!UICONTROL Bounces]](bounces.md) sì.

## Calcolo di questa metrica

Questa metrica conta il numero di visite in cui la [!UICONTROL Page] l’elemento dimensionale conteneva un solo valore univoco per l’intera visita. Se un visitatore ricarica la pagina o genera chiamate di tracciamento dei collegamenti, conteggia comunque come visita a una sola pagina. Non appena la dimensione Pagina diventa un secondo valore univoco, la visita non sarà più qualificata come visita a una sola pagina.

Vedi [Accesso singolo](single-access.md) per un confronto tra metriche.

## Conta istanze ripetute

Questa impostazione consente di specificare se le istanze ripetute vengono conteggiate nei rapporti. Per ulteriori informazioni consulta [Conta istanze ripetute](/help/components/metrics/count-repeat-instances.md).