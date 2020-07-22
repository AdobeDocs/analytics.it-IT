---
title: Visite di una singola pagina
description: Il numero di volte in cui l'elemento dimensione 'Pagina' non è stato modificato in una visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Visite di una singola pagina

*Questa pagina della guida descrive il funzionamento delle &quot;visite a pagina singola&quot; come metrica. Per ulteriori informazioni, consulta la dimensione visite[a pagina](../dimensions/single-page-visits.md)singola.*

La metrica &quot;Visite a pagina singola&quot; mostra il numero di visite in cui l’elemento dimensione [Pagina](../dimensions/page.md) conteneva un solo valore univoco per l’intera visita. Questa metrica è utile nel contesto delle dimensioni in cui si desidera visualizzare visite brevi, ma non ha regole altrettanto rigorose [dei rimbalzi](bounces.md).

## Modalità di calcolo di questa metrica

Questa metrica conta il numero di visite in cui l’elemento dimensione &#39;Pagina&#39; conteneva solo un valore univoco per l’intera visita. Se un visitatore ricarica la pagina o attiva le chiamate di tracciamento dei collegamenti, continua a conteggiare come visita a una sola pagina. Non appena la dimensione Pagina diventa un secondo valore univoco, la visita non si qualifica più come visita a una singola pagina.

Consulta Accesso [](single-access.md) singolo per un confronto tra metriche.
