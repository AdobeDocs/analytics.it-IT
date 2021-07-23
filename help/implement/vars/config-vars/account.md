---
title: account
description: Utilizza la variabile di account per determinare la suite di rapporti in cui vengono inviati i dati.
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%

---

# account

>[!IMPORTANT]
>
>Questa variabile è ritirata. Utilizza la funzione [`s.sa()`](../functions/sa-method.md) se l&#39;implementazione richiede la modifica della destinazione della suite di rapporti.

Nelle versioni precedenti di Adobe Analytics, la variabile `account` determinava la suite di rapporti a cui desideri inviare i dati. Per inviare dati ad Adobe Analytics è necessario un ID suite di rapporti.

* Se utilizzi i tag in Adobe Experience Platform, le suite di rapporti si trovano sotto il pannello a soffietto [!UICONTROL Library Management] durante la configurazione dell’estensione Adobe Analytics.
* Se utilizzi la funzione [`s_gi()`](../functions/s-gi.md) per creare un&#39;istanza di un oggetto di tracciamento di Analytics, l&#39;ID suite di rapporti esiste già come argomento obbligatorio nella funzione .
