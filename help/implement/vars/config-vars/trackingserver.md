---
title: trackingServer
description: Dominio utilizzato per inviare dati ad Adobe tramite HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
TQID: https://experienceleague.adobe.com/6H8uZ4J-mT8NcC4OiiTgtBnP8eAgaMMzxzUHkS-9kGs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 120
ht-degree: 1%

---

# trackingServer

>[!IMPORTANT]
>
>Questa variabile è obsoleta. Con la prevalenza di HTTPS, utilizza invece [`trackingServerSecure`](trackingserversecure.md).

La variabile `trackingServer` determina il dominio utilizzato da AppMeasurement per inviare dati ad Adobe tramite HTTP. Se questa variabile non è definita correttamente, l’implementazione può causare la perdita di dati.

Prima del [servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/en/docs/id-service/using/home), questa variabile determinava anche dove erano impostati i cookie di terze parti. Adobe consiglia vivamente di utilizzare il servizio ID in tutte le implementazioni, laddove possibile.

AppMeasurement utilizza `trackingServer` come fallback se [`trackingServerSecure`](trackingserversecure.md) non è impostato. Molte implementazioni precedenti non impostano `trackingServerSecure`, utilizzando `trackingServer` come fallback su pagine sicure. Data la prevalenza di HTTPS, Adobe consiglia di utilizzare `trackingServerSecure` ove possibile.
