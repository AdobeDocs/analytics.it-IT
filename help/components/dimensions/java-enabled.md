---
title: Java abilitato
description: Determina se Java è abilitato nel browser.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 5%

---

# Java abilitato

La [dimensione](overview.md) &quot;Java abilitato&quot; determina se nel browser è abilitato Java. È utile nei casi in cui desideri introdurre funzionalità basate su Java sul sito e vuoi sapere quanti visitatori hanno già Java abilitato. Per coloro che hanno Java disabilitato, puoi fornire un’alternativa o istruzioni su come abilitarlo.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa di query [`v`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati rilevando se Java è abilitato nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `v` contenente &quot;Y&quot; o &quot;N&quot; se desideri utilizzare questa dimensione.

## Elementi dimensionali

Gli elementi Dimension includono &quot;Enabled&quot; (Abilitato), &quot;Disabled&quot; (Disabilitato) e &quot;Unknown&quot; (Sconosciuto).

* **Abilitato**: Java è abilitato nel browser. La stringa di query `v` contiene il valore &quot;Y&quot;.
* **Disabilitato**: Java è disabilitato nel browser o non supporta Java. La stringa di query `v` contiene il valore &quot;N&quot;.
* **Sconosciuto**: AppMeasurement non è riuscito a determinare il supporto Java. La stringa di query `v` non è presente nella richiesta di immagine.
