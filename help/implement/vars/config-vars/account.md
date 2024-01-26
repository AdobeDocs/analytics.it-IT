---
title: account
description: Utilizza la variabile account per determinare la suite di rapporti a cui vengono inviati i dati.
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '133'
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
