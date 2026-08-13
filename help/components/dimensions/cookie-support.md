---
title: Supporto per cookie
description: Determina se il browser supporta i cookie.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
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
source-wordcount: 188
ht-degree: 7%

---

# Supporto per cookie

Il rapporto &quot;Supporto cookie&quot; [dimension](overview.md) indica se il browser supporta i cookie per un determinato hit. È utile determinare la proporzione di visitatori che utilizzano browser che supportano i cookie e di quelli che li disabilitano intenzionalmente.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalla stringa di query [`k`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement tenta di impostare un cookie denominato `s_cc`, quindi rileva se il cookie esiste. Il risultato è il valore del parametro della stringa di query `Y` (se il browser supporta e ha i cookie abilitati) o `N` (se il browser ha i cookie disabilitati). Se utilizzi AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `k` in ogni hit con il valore `Y` o `N`.

## Elementi dimensionali

Gli elementi della dimensione includono `Enabled`, `Disabled` e `Unknown`.

* **`Enabled`**: il browser supporta i cookie e li ha abilitati.
* **`Disabled`**: il browser non supporta i cookie o il visitatore li ha disabilitati.
* **`Unknown`**: AppMeasurement non è in grado di determinare il supporto dei cookie. La stringa di query `k` non è presente nella richiesta di immagine.
