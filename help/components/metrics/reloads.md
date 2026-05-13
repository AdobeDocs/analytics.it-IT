---
title: Ricariche
description: Il numero di volte in cui la pagina è stata ricaricata.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
TQID: https://experienceleague.adobe.com/Jhm8-usZH-SLOzUvNIC3hdoKDMkm9T5mnCUeeMRga7E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 132
ht-degree: 15%

---

# Ricariche

Il parametro &#39;Ricarica&#39; [metrica](overview.md) mostra il numero di volte in cui un elemento dimensione è stato presente durante un ricaricamento. In genere un ricaricamento si verifica quando un visitatore aggiorna la finestra del browser.

## Come è calcolata questa metrica

Questa metrica conta il numero di hit in cui la dimensione [Pagina](../dimensions/page.md) contiene lo stesso valore dell&#39;hit precedente.

Il concetto di ricaricamento si applica alla dimensione Pagina indipendentemente dalla dimensione utilizzata nel reporting. Se ad esempio si utilizza [eVar1](../dimensions/evar.md) come dimensione e Ricarica come metrica, nella tabella viene visualizzato il numero di volte in cui ogni valore eVar è stato presente durante un ricaricamento (due valori di pagina consecutivi). Non mostra il numero di volte in cui sono stati presenti due valori eVar1 consecutivi.
