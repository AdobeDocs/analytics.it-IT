---
title: account
description: (Ritirato) Determina la suite di rapporti a cui vengono inviati i dati.
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---

# account

>[!IMPORTANT]
>
>Questa variabile viene ritirata. Utilizza il [`s.sa()`](../functions/sa-method.md) se la tua implementazione richiede la modifica della destinazione della suite di rapporti.

Nelle versioni precedenti di Adobe Analytics, il `account` ha determinato la suite di rapporti a cui desideri inviare i dati. Per inviare dati ad Adobe Analytics è necessario un ID suite di rapporti.

* Se utilizzi il Web SDK, le suite di rapporti si trovano nelle impostazioni del servizio Adobe Analytics all’interno dello stream di dati a cui il Web SDK invia i dati.
* Se utilizzi l’estensione Adobe Analytics, le suite di rapporti risiedono nel [!UICONTROL Library Management] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.
* Se si utilizza [`s_gi()`](../functions/s-gi.md) per creare un&#39;istanza di un oggetto di tracciamento Analytics, gli ID suite di rapporti esistono già come argomento obbligatorio nella funzione.
