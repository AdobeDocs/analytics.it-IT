---
title: Visite a pagina singola (metriche)
description: Il numero di volte in cui l’elemento dimensione "Pagina" non è cambiato in una visita.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 8%

---

# Visite a pagina singola

*Questa pagina della guida descrive come funziona il funzionamento di &quot;Visite a pagina singola&quot; come metrica. Consulta la [Visite a pagina singola](../dimensions/single-page-visits.md) per ulteriori informazioni.*

Il [!UICONTROL Single page visits] La metrica mostra il numero di visite in cui [Pagina](../dimensions/page.md) l’elemento dimensionale conteneva un solo valore univoco per l’intera visita. Questa metrica è utile nel contesto di dimensioni in cui desideri visualizzare visite brevi, ma non ha il rigore di una regola come [[!UICONTROL Bounces]](bounces.md) sì.

## Modalità di calcolo di questa metrica

Questa metrica conta il numero di visite in cui [!UICONTROL Page] l’elemento dimensionale conteneva un solo valore univoco per l’intera visita. Se un visitatore ricarica la pagina o genera chiamate di tracciamento dei collegamenti, conta ancora come una visita a pagina singola. Non appena la dimensione Pagina diventa un secondo valore univoco, la visita non si qualifica più come visita a pagina singola.

Consulta [Accesso singolo](single-access.md) per un confronto tra metriche.

## Conta istanze ripetute

Questa impostazione consente di specificare se le istanze ripetute vengono conteggiate nei rapporti. Per ulteriori informazioni, consulta [Conta istanze ripetute](/help/components/metrics/count-repeat-instances.md).