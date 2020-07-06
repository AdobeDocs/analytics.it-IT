---
title: account
description: Utilizzate la variabile di account per determinare la suite di rapporti a cui vengono inviati i dati.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 1%

---


# account

>[!IMPORTANT]
>
>Questa variabile è ritirata. Utilizzate la [`s.sa()`](../functions/sa-method.md) funzione se la vostra implementazione richiede che modificate la destinazione della suite di rapporti.

Nelle versioni precedenti di Adobe  Analytics, la `account` variabile determinava la suite di rapporti a cui si desidera inviare i dati. Per inviare dati ad Adobe  Analytics è necessario un ID suite di rapporti.

* Se utilizzate  lancio di Adobe Experience Platform, le suite di rapporti si trovano sotto la struttura di [!UICONTROL Library Management] navigazione quando configurate l&#39;estensione Adobe  Analytics.
* Se si utilizza la [`s_gi()`](../functions/s-gi.md) funzione per creare un&#39;istanza di un oggetto di tracciamento Analytics , l&#39;ID suite di rapporti esiste già come argomento obbligatorio nella funzione.
