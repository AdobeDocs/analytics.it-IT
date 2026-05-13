---
title: Ricavi
description: Importo monetario dei prodotti acquistati in tutti gli ordini.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
TQID: https://experienceleague.adobe.com/GJsQWf7h-TihzyNUN6e3VGzOUNyxYD1esuvXet5LM1c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 6%

---

# Ricavi

La metrica &quot;Ricavi&quot; [metrica](overview.md) mostra la quantità monetaria di prodotti acquistati in tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito ai ricavi. Ad esempio, puoi visualizzare le campagne principali (utilizzando la dimensione [Codice di tracciamento](../dimensions/tracking-code.md)) o i termini di ricerca interni principali (utilizzando un [eVar](../dimensions/evar.md)).

## Come è calcolata questa metrica

Per ogni hit in cui esiste `purchase` nella variabile [`events`](/help/implement/vars/page-vars/events/event-purchase.md), somma il campo &quot;Prezzo&quot; all&#39;interno della variabile [`products`](/help/implement/vars/page-vars/products.md).

Questa metrica si basa sulla variabile [currencyCode](/help/implement/vars/config-vars/currencycode.md) se la valuta nella pagina è diversa dalla valuta nativa della suite di rapporti.
