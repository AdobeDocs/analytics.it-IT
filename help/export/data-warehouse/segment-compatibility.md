---
title: Compatibilità del segmento Data Warehouse
description: Scopri quali definizioni di segmenti sono valide per l’utilizzo in Data Warehouse.
feature: Data Warehouse
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 425
ht-degree: 0%

---

# Compatibilità del segmento Data Warehouse

Non tutti i segmenti generati nel Generatore di segmenti possono essere utilizzati in Data Warehouse. Utilizzare questa pagina per scoprire quali definizioni di segmenti sono compatibili con Data Warehouse in modo che sia disponibile per la selezione quando si [crea una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Un segmento è compatibile con Data Warehouse solo quando **entrambi** dei seguenti valori sono true:

* **Componenti supportati**: il segmento utilizza solo dimensioni e metriche supportate da Data Warehouse.
* **Struttura supportata**: la struttura del segmento segue le regole applicate da Data Warehouse.

Se una delle due condizioni non è soddisfatta, il segmento non viene visualizzato come opzione quando si crea una richiesta Data Warehouse e viene visualizzato un errore se si seleziona una suite di rapporti virtuale che contiene un segmento non compatibile.

## Componenti supportati

Poiché un segmento viene valutato in base agli stessi dati della richiesta a cui è applicato, **qualsiasi componente non supportato in una richiesta Data Warehouse non è supportato in un segmento.** Per l&#39;elenco completo delle dimensioni e delle metriche non supportate da Data Warehouse, vedere [Supporto dei componenti in Data Warehouse](component-support.md).

Oltre alle dimensioni e alle metriche elencate in [Supporto componenti](component-support.md), in una *richiesta* di Data Warehouse sono disponibili le dimensioni seguenti, ma **non possono essere utilizzate all&#39;interno di una definizione di segmento**:

* [[!UICONTROL Day of Month]](/help/components/dimensions/day-of-month.md)
* [[!UICONTROL Day of Week]](/help/components/dimensions/day-of-week.md)
* [[!UICONTROL Day of Year]](/help/components/dimensions/day-of-year.md)
* [[!UICONTROL Hour of Day]](/help/components/dimensions/hour-of-day.md)
* [[!UICONTROL Marketing Channels]](/help/components/dimensions/marketing-channel.md) (utilizzare [[!UICONTROL Last touch channel]](/help/components/dimensions/last-touch-channel.md))
* [[!UICONTROL Month of Year]](/help/components/dimensions/month-of-year.md)
* [[!UICONTROL Pages Not Found]](/help/components/dimensions/pages-not-found.md) (utilizzare [[!UICONTROL Page type error]](/help/components/dimensions/pages-not-found.md))
* [[!UICONTROL Quarter of Year]](/help/components/dimensions/quarter-of-year.md)
* [[!UICONTROL Weekday/Weekend]](/help/components/dimensions/weekday-weekend.md)

## Struttura supportata

Anche quando un segmento utilizza solo componenti supportati, la sua struttura deve seguire le regole che Data Warehouse applica. Le strutture di segmenti sono completamente supportate, parzialmente supportate o non supportate:

**Supportato**:

* **Stacking dei segmenti**: è possibile applicare più segmenti a una singola richiesta Data Warehouse.
* **Contenitori nidificati**: supportati, forniti con ambito ridotto a ogni livello (visitatore → visita → hit). I contenitori che aumentano nell’ambito non sono supportati.

**Parzialmente supportato**:

* **Escludi contenitori**: supportato solo al livello superiore. Data Warehouse supporta solo i segmenti che possono essere espressi come `A AND NOT B`, ovvero **includi questa caratteristica** e **escludi questa caratteristica**. I contenitori di esclusione nidificati all’interno di altri contenitori non sono supportati.
* **AND/OR logic**: supportato con limitazioni. Quando si utilizza un contenitore `exclusion` o `without` in combinazione con la logica AND/OR, sono supportati solo i segmenti che possono essere riscritti come `A AND NOT B`.

**Non supportato**:

* **Segmenti sequenziali**: i segmenti che utilizzano l&#39;operatore THEN per definire sequenze di navigazione per i visitatori ordinati non sono supportati.
* **&quot;È uguale a uno di&quot; e &quot;Non è uguale a nessuno di&quot; operatori**: questi operatori non sono supportati nei segmenti Data Warehouse.

## Segmenti utilizzati come dimensioni

Quando utilizzi un segmento come dimensione in un rapporto di Data Warehouse, il rapporto restituisce una colonna contenente `"0"` o `"1"`:

* **`"0"`**: l&#39;elemento dimensione non soddisfa i criteri del segmento.
* **`"1"`**: l&#39;elemento dimensione ha soddisfatto i criteri del segmento.
