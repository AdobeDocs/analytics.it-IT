---
title: account
description: (Ritirato) Determina la suite di rapporti a cui vengono inviati i dati.
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '129'
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
