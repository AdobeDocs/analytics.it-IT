---
title: account
description: (Ritirato) Determina la suite di rapporti a cui vengono inviati i dati.
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/ICQkj-Eo29jve35GewuZUKOPIr01g-WjhbyztrAO0jI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 129
ht-degree: 1%

---

# account

>[!IMPORTANT]
>
>Questa variabile viene ritirata. Utilizza la funzione [`s.sa()`](../functions/sa-method.md) se l&#39;implementazione richiede la modifica della destinazione della suite di rapporti.

Nelle versioni precedenti di Adobe Analytics, la variabile `account` ha determinato la suite di rapporti a cui desideri inviare i dati. Per inviare dati ad Adobe Analytics è necessario un ID suite di rapporti.

* Se utilizzi il Web SDK, le suite di rapporti si trovano nelle impostazioni del servizio Adobe Analytics all’interno dello stream di dati a cui il Web SDK invia i dati.
* Se utilizzi l&#39;estensione Adobe Analytics, le suite di rapporti risiedono nel Pannello a soffietto [!UICONTROL Library Management] durante la configurazione dell&#39;estensione Adobe Analytics.
* Se utilizzi la funzione [`s_gi()`](../functions/s-gi.md) per creare un&#39;istanza di un oggetto di tracciamento Analytics, gli ID suite di rapporti esistono già come argomento obbligatorio nella funzione.
