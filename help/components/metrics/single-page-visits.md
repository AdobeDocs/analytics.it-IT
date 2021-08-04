---
title: Visite a pagina singola
description: Il numero di volte in cui l’elemento della dimensione "Pagina" non è stato modificato in una visita.
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 98463103e6e2ba19d11629d40dacc0c02f5b33c9
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 10%

---

# Visite a pagina singola

*Questa pagina di aiuto descrive il funzionamento di &quot;visite a pagina singola&quot; come metrica. Per ulteriori informazioni, consulta la dimensione [Visite a pagina singola](../dimensions/single-page-visits.md) .*

La metrica [!UICONTROL Single page visits] mostra il numero di visite in cui l’elemento della dimensione [Pagina](../dimensions/page.md) conteneva un solo valore univoco per l’intera visita. Questa metrica è utile nel contesto delle dimensioni in cui desideri visualizzare visite brevi, ma non ha lo stesso rigore di una regola di quanto fa [[!UICONTROL Bounces]](bounces.md).

## Calcolo di questa metrica

Questa metrica conta il numero di visite in cui l’elemento della dimensione [!UICONTROL Page] conteneva un solo valore univoco per l’intera visita. Se un visitatore ricarica la pagina o genera chiamate di tracciamento dei collegamenti, conteggia comunque come visita a una sola pagina. Non appena la dimensione Pagina diventa un secondo valore univoco, la visita non sarà più qualificata come visita a una sola pagina.

Per un confronto tra metriche, consulta [Accesso singolo](single-access.md) .

## Conta istanze ripetute

Questa impostazione consente di specificare se le istanze ripetute vengono conteggiate nei rapporti. Per ulteriori informazioni, consulta [Contare istanze ripetute](/help/components/metrics/count-repeat-instances.md).