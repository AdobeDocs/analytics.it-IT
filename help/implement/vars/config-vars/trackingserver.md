---
title: trackingServer
description: Dominio utilizzato per inviare dati ad Adobe tramite HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 1%

---

# trackingServer

>[!IMPORTANT]
>
>Questa variabile è obsoleta. Con la prevalenza di HTTPS, utilizza invece [`trackingServerSecure`](trackingserversecure.md).

La variabile `trackingServer` determina il dominio utilizzato da AppMeasurement per inviare dati ad Adobe tramite HTTP. Se questa variabile non è definita correttamente, l’implementazione può causare la perdita di dati.

Prima del [servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/en/docs/id-service/using/home), questa variabile determinava anche dove erano impostati i cookie di terze parti. Adobe consiglia vivamente di utilizzare il servizio ID in tutte le implementazioni, laddove possibile.

AppMeasurement utilizza `trackingServer` come fallback se [`trackingServerSecure`](trackingserversecure.md) non è impostato. Molte implementazioni precedenti non impostano `trackingServerSecure`, utilizzando `trackingServer` come fallback su pagine sicure. Data la prevalenza di HTTPS, Adobe consiglia di utilizzare `trackingServerSecure` ove possibile.
