---
description: Nel passaggio 1 della Creazione guidata richieste è possibile applicare un livello di granularità alla richiesta di dati. Granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.
title: Granularità
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
TQID: https://experienceleague.adobe.com/26j4Fernl4bfuYeyuVVzw1K5hZvNSD6pDUVOfEc0J8s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 161
ht-degree: 1%

---

# Granularità

{{legacy-arb}}

Nel passaggio 1 della Creazione guidata richieste è possibile applicare un livello di granularità alla richiesta di dati. Granularità specifica il livello di dettaglio basato sul tempo incluso nel rapporto.

I valori validi sono Ora, Giorno, Settimana, Mese, Trimestre, Anno e Aggregato.

## Elaborazione della granularità in Report Builder

Supponiamo di scegliere un intervallo di date per un mese con granularità [!UICONTROL Month]. Le richieste mostrano i totali per la metrica in base ai dati relativi a un mese esatto. Se l’intervallo di date della richiesta si estende su un trimestre, il rapporto mostra tre cifre: una per ogni unità di mese o frazione di unità. Se oggi è il 18 marzo, scegliendo l’ultimo trimestre si restituisce un dato per il 1° gennaio - 31 gennaio, un altro per il 1° febbraio - 28 febbraio e un dato finale per il 1° marzo - 17 marzo.
