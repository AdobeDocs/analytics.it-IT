---
title: Ricavi
description: Importo monetario dei prodotti acquistati in tutti gli ordini.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
source-git-commit: a1fbd3f483d3a236fe5dc3246f5e90c1b3f51ba9
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 6%

---

# Ricavi

La metrica &quot;Ricavi&quot; [metrica](overview.md) mostra la quantità monetaria di prodotti acquistati in tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito ai ricavi. Ad esempio, puoi visualizzare le campagne principali (utilizzando la dimensione [Codice di tracciamento](../dimensions/tracking-code.md)) o i termini di ricerca interni principali (utilizzando un [eVar](../dimensions/evar.md)).

## Come è calcolata questa metrica

Per ogni hit in cui esiste `purchase` nella variabile [`events`](/help/implement/vars/page-vars/events/event-purchase.md), somma il campo &quot;Prezzo&quot; all&#39;interno della variabile [`products`](/help/implement/vars/page-vars/products.md).

Questa metrica si basa sulla variabile [currencyCode](/help/implement/vars/config-vars/currencycode.md) se la valuta nella pagina è diversa dalla valuta nativa della suite di rapporti.
